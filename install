$ErrorActionPreference = "Stop"

function Show-Menu {
    Clear-Host
    Write-Host ""
    Write-Host " crit installer"
    Write-Host " use this on school pcs to get crit"
    Write-Host " requested by like 2 people"
    Write-Host ""
    Write-Host " download 1: crit full"
    Write-Host " download 2: crit lite"
    Write-Host ""

    return Read-Host ">>>"
}

while ($true) {
    $choice = Show-Menu

    switch ($choice) {
        "1" {
            $repo = "snigglaberry/critlauncher"
            $assetName = "crit.exe"
        }
        "2" {
            $repo = "snigglaberry/crit-lite"
            $assetName = "crit-lite.exe"
        }
        default {
            continue
        }
    }

    try {
        Write-Host ""
        Write-Host "Fetching latest release..."

        $headers = @{
            "User-Agent" = "CritInstaller"
        }

        $releaseUrl = "https://api.github.com/repos/$repo/releases/latest"
        $release = Invoke-RestMethod -Uri $releaseUrl -Headers $headers

        $asset = $release.assets |
            Where-Object { $_.name -ceq $assetName } |
            Select-Object -First 1

        if (-not $asset) {
            throw "$assetName was not found in the latest release."
        }

        # Create crit folder in the current directory
        $targetDir = Join-Path (Get-Location).Path "crit"
        New-Item -ItemType Directory -Path $targetDir -Force | Out-Null

        $outputPath = Join-Path $targetDir $assetName

        Write-Host "Downloading $assetName..."
        Invoke-WebRequest -Uri $asset.browser_download_url -OutFile $outputPath

        Write-Host ""
        Write-Host "Download complete!"
        Write-Host "Saved to: $outputPath"
    }
    catch {
        Write-Host ""
        Write-Host "Download failed: $($_.Exception.Message)" -ForegroundColor Red
    }

    Write-Host ""
    Read-Host "Press Enter to return to menu"
}
