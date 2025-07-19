# Crypto Link Share | WebApp

CryptoLinkShare is a static, client-side web app that encrypts URLs via AES-256, generates opaque shareable links and QR codes, and persists mappings in localStorage. Easily export or import your mapping as JSON. No server required—pure HTML, CSS, and JavaScript.

[![Try Demo](https://img.shields.io/badge/Try%20Demo-Online-blue?style=for-the-badge)](https://bocaletto-luca.github.io/CryptoLinkShare/index.html)

---

## Table of Contents

- [Features](#features)  
- [Demo](#demo)  
- [Getting Started](#getting-started)  
- [Usage](#usage)  
- [How It Works](#how-it-works)  
- [File Structure](#file-structure)  
- [Customization](#customization)  
- [Contributing](#contributing)  
- [License](#license)  
- [Author](#author)  

---

## Features

- AES-256 client-side encryption (via CryptoJS)  
- Opaque shareable links (`#/e/{token}`)  
- Live QR code generation (via QRCode.js)  
- Persistent mapping in `localStorage`  
- Export/import mapping as `mapping.json`  
- Full static implementation: **HTML**, **CSS**, **JavaScript**, **JSON**  
- No backend required—works on any static host or local HTTP server  

---

## Demo

Open the live demo on GitHub Pages:  
https://bocaletto-luca.github.io/CryptoLinkShare/index.html

---

## Getting Started

These instructions will get you a copy of the project up and running on your local machine.

### Prerequisites

A modern browser and a simple static HTTP server. For example:

- **Python 3**  
  ```bash
  python3 -m http.server 8000
  ```
- **Node.js**  
  ```bash
  npx http-server . -p 8000
  ```

### Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/bocaletto-luca/CryptoLinkShare.git
   cd CryptoLinkShare
   ```

2. Start your HTTP server in this directory:

   ```bash
   python3 -m http.server 8000
   ```

3. Open your browser at <http://localhost:8000> and enjoy!

---

## Usage

1. **Generate Secure Link**  
   - Paste any URL into the input field and click **Generate Secure Link**.  
   - The page displays:
     - A shareable encrypted link (`#/e/{token}`)  
     - A QR code you can scan  
     - A **Copy** button to copy the link to your clipboard  

2. **Share**  
   - Send the encrypted link or QR code to recipients.  
   - When they visit the link on the same page, they will be automatically redirected.

3. **Export Mapping**  
   - Click **Export Mapping** to download `mapping.json`, containing all `{token: originalURL}` pairs.

4. **Import Mapping**  
   - Click **Import Mapping** and select a previously exported `mapping.json` to restore your mapping.

---

## How It Works

- **Encryption**: Uses [CryptoJS](https://github.com/brix/crypto-js) AES-256 to encrypt URLs into opaque tokens.  
- **Decryption & Redirect**: When visiting `index.html#/e/{token}`, the app decrypts the token and performs a client-side redirect.  
- **QR Codes**: Utilizes [QRCode.js](https://github.com/davidshimjs/qrcodejs) to render a scannable QR code for each encrypted link.  
- **Persistence**: Stores the token-to-URL mapping in `localStorage` for quick recall; export/import provides backup and portability.  
- **Client-Side Only**: All logic lives in a single HTML file—no server-side dependencies or databases.

---

## File Structure

```
CryptoLinkShare/
├── index.html      # Single-page app with embedded HTML, CSS, JS
├── mapping.json    # Optional export/import file for token→URL mapping
└── README.md       # This file
```

---

## Customization

- **Passphrase**: Edit the `SECRET` constant in the inline `<script>` of `index.html`.  
- **Styling**: Modify the `<style>` block in `index.html` or convert it to an external `style.css`.  
- **Routing Prefix**: Change the `#/e/` prefix in the script if preferred.  

---

## Contributing

Contributions are welcome! To propose improvements or report issues:

1. Fork the repository  
2. Create a new branch (`git checkout -b feature/my-feature`)  
3. Commit your changes (`git commit -m "Add my feature"`)  
4. Push to your fork (`git push origin feature/my-feature`)  
5. Open a Pull Request  

Please ensure your code adheres to the existing style and is well-tested.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Author

**Bocaletto Luca**  
- GitHub: [@bocaletto-luca](https://github.com/bocaletto-luca)  
- Repository: [CryptoLinkShare](https://github.com/bocaletto-luca/CryptoLinkShare)
