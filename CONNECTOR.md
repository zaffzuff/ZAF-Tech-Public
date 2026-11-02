# ZAF Tech Node Connector for Windows

## Install

1. Download `ZAF-TECH-Node-Connector-Setup.exe` from [Releases](https://github.com/zaffzuff/ZAF-Tech-Public/releases/latest).
2. Run the installer on your Windows x64 computer. Review the optional Windows-startup and launch selections.
3. With your own Pi Node/Docker installation running, open [ZAF Tech](https://zaf-tech.vercel.app) and select **Network → Node**.

The installer includes the tray application and its worker. It is not code-signed; Windows may display an unknown-publisher notice. Obtain the package from this repository and verify its checksum before deciding whether to install it.

## Verify the download

Download `ZAF-TECH-Node-Connector-SHA256SUMS.txt` from the same release. In PowerShell, run:

```powershell
Get-FileHash .\ZAF-TECH-Node-Connector-Setup.exe -Algorithm SHA256
```

Compare the hash with the installer entry in the checksum file. A matching hash verifies file integrity; it is not a substitute for a code-signing certificate.

## Local diagnostics and privacy

- The worker binds only to `127.0.0.1:39100`.
- Production browser access is limited to `https://zaf-tech.vercel.app` by default, with local development origins also allowed. Foreign origins and invalid Host headers are rejected before diagnostics.
- It reads Docker/WSL and Pi Node status and keeps a local diagnostic history. It does not upload that history to a central server by itself.
- It does not start, stop or reconfigure your Pi Node. Tray controls start or stop the Connector itself.
- It never requests Pi wallet credentials or recovery words, signs transactions, or takes payments.
- Node protocols 27 and 28 are recognized. Other protocols are reported as unknown compatibility.

## Türkçe kurulum

1. [Releases](https://github.com/zaffzuff/ZAF-Tech-Public/releases/latest) sayfasından **Setup.exe** dosyasını indirin.
2. Windows x64 bilgisayarınızda kurulum seçeneklerini inceleyerek yükleyin. Kurulum, Connector ve yardımcı worker dosyalarını birlikte kurar.
3. Pi Node/Docker çalışırken [ZAF Tech](https://zaf-tech.vercel.app) içerisinde **Network → Node** bölümünü açın.

Paket kod imzalı değildir; Windows bilinmeyen yayıncı bildirimi gösterebilir. Kurmadan önce dosyanın bu repodan geldiğini ve SHA-256 değerinin aynı sürümün doğrulama dosyasıyla eşleştiğini kontrol edin.

Connector yalnızca yerel teşhis verilerini okur. Pi Node ayarlarınızı değiştirmez. Cüzdan kurtarma kelimelerinizi, parolanızı veya özel anahtarınızı hiçbir zaman istemez.
