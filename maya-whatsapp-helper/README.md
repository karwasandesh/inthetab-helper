# Maya WhatsApp Helper

A small app for Mac and Windows that lets **Maya Studio** add products (photos, name and price) to The Maya Store's
WhatsApp Business catalog. It links to WhatsApp the same way WhatsApp Web does, from your own computer.

There's nothing else to install: no Node.js, no Python, no terminal.

| Your computer | Download |
|---|---|
| Mac (Apple Silicon or Intel, macOS 11 or later) | [Maya-WhatsApp-Helper.dmg](https://github.com/karwasandesh/inthetab-helper/releases/download/maya-whatsapp-v1.0.0/Maya-WhatsApp-Helper.dmg) |
| Windows 10 or 11 (64-bit) | [Maya-WhatsApp-Helper.exe](https://github.com/karwasandesh/inthetab-helper/releases/download/maya-whatsapp-v1.0.0/Maya-WhatsApp-Helper.exe) |

Maya Studio also shows the right download for your computer when you click **Add to catalog**. Phones and tablets
aren't supported.

## Install on a Mac

1. Download `Maya-WhatsApp-Helper.dmg`, open it, and drag **Maya WhatsApp Helper** into **Applications**.
2. Open **Maya WhatsApp Helper** from Applications.
3. The first time, macOS says it *"could not verify"* the app (it isn't signed with an Apple certificate yet).
   Click **Done**, not *Move to Bin*.
4. Open **System Settings → Privacy & Security**, scroll down to the message about Maya WhatsApp Helper, and click
   **Open Anyway**. Confirm with your password or Touch ID.
5. The first time it sets itself up (about a minute), then Maya Studio opens in your browser.

You only do steps 3–4 once. The helper runs in the background with no window or Dock icon.

## Install on Windows

1. Download `Maya-WhatsApp-Helper.exe` and double-click it.
2. If Windows shows *"Windows protected your PC"*, click **More info**, then **Run anyway**.
3. Maya Studio opens in your browser.

The helper runs in the background with no window.

## Using it

1. Open **Maya WhatsApp Helper**. Maya Studio opens by itself.
2. Click **Add to catalog**.
3. The first time, click **Log in with QR code**. On the store phone open **WhatsApp Business → Settings (or ⋮) →
   Linked devices → Link a device** and scan the code. It stays linked, so next time you skip this.
4. Add photos, the name and the price, then click **Add to WhatsApp catalog**. WhatsApp checks each new product,
   so it can take a little while to appear.

Use **Chrome or Edge**. They may ask once whether the page may *"access other apps and services on this device"* or
devices on your local network: click **Allow**, that's Maya Studio talking to the helper.

To stop the helper, click **Stop helper** in the **Add to catalog** window.

## Please read: WhatsApp risk

The helper uses [Baileys](https://github.com/WhiskeySockets/Baileys), an unofficial WhatsApp Web connection. WhatsApp
doesn't approve it and can restrict or ban a number that looks automated. To keep the number safe:

- Products are added **one at a time**. There's no bulk upload, and the helper waits at least 30 seconds between products.
- Add products at a normal pace, a few at a time.

## Privacy and security

- **Your WhatsApp stays on your computer.** The link (like a WhatsApp Web login) is saved only on this computer. Maya
  Studio's servers never see it.
- **Only Maya Studio can use it.** The helper listens on `127.0.0.1:47214`, so other computers on your network can't
  reach it, and it refuses requests from any other website.
- **Verified setup.** On a Mac it downloads Node.js from nodejs.org on first open and checks it against a fixed SHA-256
  checksum. On Windows, Node.js is built in.
- Each release lists SHA-256 checksums in `SHA256SUMS.txt`.

## Troubleshooting

| What you see | What to do |
|---|---|
| Studio says the helper isn't running | Open Maya WhatsApp Helper again. If it's already open, reload the page. |
| Chrome or Edge blocked the connection | Click the icon at the left of the address bar, allow access to apps or devices on this computer, then reload. |
| Safari can't reach the helper | Use Chrome or Edge. |
| A new QR code appears | The link was removed on the phone or expired. Scan again. |
| "Wait …s before adding the next product" | The 30-second safety gap. Wait and click again. |
| Setup failed on first open (Mac) | Check your internet connection and open the app again. |

The Mac log is at `~/Library/Logs/Maya WhatsApp Helper.log`.

## Uninstall

**Mac:** click **Stop helper** in Maya Studio, move **Maya WhatsApp Helper** from Applications to the Bin, then
delete `~/Library/Application Support/Maya WhatsApp Helper` and `~/Library/Logs/Maya WhatsApp Helper.log`.

**Windows:** click **Stop helper** in Maya Studio, delete `Maya-WhatsApp-Helper.exe`, then delete the folder
`%LOCALAPPDATA%\Maya WhatsApp Helper`.

On the phone, remove **Maya Studio** under **Linked devices**.

## Licence and source

The helper is free software under the [GNU GPL v3](LICENSE), because it includes `libsignal` (GPL-3.0). Every release
includes `Maya-WhatsApp-Helper-source.zip` with the full source. Third-party software is listed in
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
