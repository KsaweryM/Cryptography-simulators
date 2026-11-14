# Cryptography simulators

Interactive pages, one per cryptography topic, made to accompany a cryptography course. Plain HTML, CSS and JavaScript, one file per simulator,
no build step and no external files, so they also work offline (open `index.html` in a browser).

| Folder | Topic | Simulator |
|---|---|---|
| `math/` | Mathematics for cryptography | Contents only for now: 9 chapters and 60 sections in learning order, from number theory to lattices, each marked "coming soon" |
| `pki/` | Certificates and PKI | Contents only for now: 10 chapters and 46 sections, from X.509 and chains of trust to revocation, incidents and post-quantum certificates, each marked "coming soon" |
| `aes/` | AES and its modes | AES explorer (black box, inside, one round, the modes ECB/CTR/GCM/XTS, comparison) |
| `rc4/` | Stream ciphers and RC4 | RC4 explorer (black box, KSA, PRGA, the weaknesses) |
| `chacha20/` | Salsa20 and ChaCha20 | ChaCha20 explorer (4 steps: black box, inside, one round, one operation) |
| `rsa/` | Public-key cryptography and RSA | RSA explorer (black box, making the keys, one power mod n, textbook RSA is not enough) |
| `diffie-hellman/` | Diffie-Hellman and ElGamal | Diffie-Hellman explorer (black box, the powers of g, Mallory in the middle, ElGamal, one power) |
| `elliptic-curves/` | Elliptic curves | Elliptic-curve explorer (black box, adding points, modulo 17, one addition) |

## Publishing on GitHub Pages

1. Create an empty repository on GitHub (for example `CryptographySimulators`) and push this folder to it.
2. Settings → Pages → Build and deployment → Source: "Deploy from a branch", Branch: `main`, folder: `/ (root)`.
3. After a minute the site is at `https://<user>.github.io/<repository>/`, and for example the ChaCha20
   explorer at `https://<user>.github.io/<repository>/chacha20/`.

All links are relative, so the site works the same from a local folder and from GitHub Pages. The empty file
`.nojekyll` tells GitHub Pages to serve the files without processing them.

## Adding a simulator

1. Make a folder next to `index.html`, for example `rc4/`, with the page in `rc4/index.html`.
2. In `index.html`, fill in `href: "rc4/index.html"` for its topic in the `TOPICS` list, or add a new entry
   with `en` and `pl` texts (`topic`, `name`, `desc`, `chips`). Cards appear in the order of the list.
3. In the new page, link back with `href="../index.html"` and keep the language in `localStorage` under the
   key `cryptoSimLang`, so the PL/EN choice is shared by all pages.
