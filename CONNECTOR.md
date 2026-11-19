# ZAF Tech Node Agent v1.9.9 for Windows

## Install

1. Download `ZAF-Tech-Node-Agent-v1.9.9-Setup.exe` from [Releases](https://github.com/zaffzuff/ZAF-Tech-Public/releases/latest).
2. Run the installer on your Windows x64 computer. Review the optional Windows-startup and launch selections.
3. With your own Pi Node/Docker installation running, open [ZAF Tech](https://zaf-tech.vercel.app) and select **Network → Node**.

The installer includes the tray application and its worker. It is not code-signed; Windows may display an unknown-publisher notice. Obtain the package from this repository and verify its checksum before deciding whether to install it.

## Verify the download

Download `ZAF-TECH-Node-Connector-SHA256SUMS.txt` from the same release. In PowerShell, run:

```powershell
Get-FileHash .\ZAF-Tech-Node-Agent-v1.9.9-Setup.exe -Algorithm SHA256
```

Compare the hash with the installer entry in the checksum file. A matching hash verifies file integrity; it is not a substitute for a code-signing certificate.

## Local diagnostics and privacy

- The worker binds only to `127.0.0.1:39100`.
- Production browser access is limited to `https://zaf-tech.vercel.app` by default, with local development origins also allowed. Foreign origins and invalid Host headers are rejected before diagnostics.
- It reads Docker/WSL and Pi Node status and keeps a local diagnostic history. It does not upload that history to a central server by itself.
- It does not start, stop or reconfigure your Pi Node. Tray controls start or stop the Agent itself.
- It never requests Pi wallet credentials or recovery words, signs transactions, or takes payments.
- Node protocols 27 and 28 are recognized. Other protocols are reported as unknown compatibility.

## Türkçe kurulum

1. [Releases](https://github.com/zaffzuff/ZAF-Tech-Public/releases/latest) sayfasından **Setup.exe** dosyasını indirin.
2. Windows x64 bilgisayarınızda kurulum seçeneklerini inceleyerek yükleyin. Kurulum, Agent ve yardımcı worker dosyalarını birlikte kurar.
3. Pi Node/Docker çalışırken [ZAF Tech](https://zaf-tech.vercel.app) içerisinde **Network → Node** bölümünü açın.

Paket kod imzalı değildir; Windows bilinmeyen yayıncı bildirimi gösterebilir. Kurmadan önce dosyanın bu repodan geldiğini ve SHA-256 değerinin aynı sürümün doğrulama dosyasıyla eşleştiğini kontrol edin.

Agent yalnızca yerel teşhis verilerini okur. Pi Node ayarlarınızı değiştirmez. Cüzdan kurtarma kelimelerinizi, parolanızı veya özel anahtarınızı hiçbir zaman istemez.

## New in v1.9.7

- Real country boundaries and local country-level connection summaries in ZAF Tech. Incoming Windows TCP observations and authenticated Core peers retain separate source labels. Raw peer addresses are not sent to a geolocation service.
- Country lookup uses the bundled DB-IP Country Lite November 2026 database, licensed CC BY 4.0: https://db-ip.com/db/download/ip-to-country-lite. Country locations are approximate.
- On explicit request only, the local worker reads the Node UUID used by Pi Desktop from its own query log (registry fallback) and sends that identifier only to Pi’s sync.minepi.com service to retrieve the published availability record, up to 90 days. Logs and the identifier are not uploaded to ZAF Tech.
- Existing installation identity, local history and startup preference are preserved.

The personal bonus journal is a separate ZAF Tech feature requiring a verified Pi session; entries are manual and private to that app-scoped identity.

## Shared Windows Agent / Ortak Windows Agent (v1.9.9)

**Windows: ZAF Tech Node Agent. SoloHost: ZAF Tech Node Connector.** One Windows installation supplies local read-only data to both applications. SoloHost integration is being developed separately; the Windows rename does not by itself enable its dashboard.

Bu sürüm mevcut kurulumun üzerine yükselir. Kurulum kimliği, Node geçmişi, yerel API adresi ve dahili çalıştırılabilir dosya adları uyumluluk için korunur. Önceki başlangıç girdileri ve menü kısayolları yenilenir; ikinci bir Agent kurulmaz. Pi Node ve Docker yapılandırması değiştirilmez.

Legacy executable names and the API identifier `zaf-node-connector` remain intentional compatibility identifiers. Old releases remain available for rollback.

## Docker system inventory (v1.9.9)

The fixed read-only /system endpoint reports Docker versions, system capacity and container inventory. Environment values, mounts, command lines, host paths and raw container IDs are excluded. This supports the Docker panel of the separate SoloHost app. Existing ZAF Tech clients remain compatible.
