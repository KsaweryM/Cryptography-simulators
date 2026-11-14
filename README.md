# Cryptography simulators

Interactive pages that show how cryptographic algorithms work, from the outside in: first the whole algorithm as a
black box with live values, then what is inside it, step by step, down to a single operation.

**Live site:** https://ksawerym.github.io/Cryptography-simulators/

- English and Polish (PL/EN buttons), light and dark mode.
- Plain HTML, CSS and JavaScript: one self-contained file per simulator, no build step, no libraries, no network.
  Everything runs in your browser and nothing you type is sent anywhere.
- Every simulator that computes something checks itself on load against official test vectors
  (RFCs, NIST and IEEE standards, textbook examples) and shows the result in its sidebar.

## Topics

| Folder | Topic | What is there |
|---|---|---|
| `math/` | Mathematics for cryptography | Contents for now: 9 chapters and 60 sections in learning order, from number theory to lattices |
| `aes/` | AES and its modes | Explorer: black box, inside, one round, the modes ECB, CTR, GCM and XTS, comparison |
| `rc4/` | Stream ciphers and RC4 | Explorer: black box, key scheduling (KSA), producing bytes (PRGA), the weaknesses |
| `chacha20/` | Salsa20 and ChaCha20 | Explorer: black box, inside, one round, one operation |
| `rsa/` | Public-key cryptography and RSA | Explorer: black box, making the keys, one power mod n, why textbook RSA is not enough |
| `diffie-hellman/` | Diffie-Hellman and ElGamal | Explorer: black box, the powers of g, Mallory in the middle, ElGamal, one power |
| `elliptic-curves/` | Elliptic curves | Explorer: black box, adding points, the curve modulo 17, one addition |
| `pki/` | Certificates and PKI | Contents for now: 10 chapters and 46 sections, from X.509 to post-quantum certificates |

More topics are listed on the site as "coming soon": classical ciphers, randomness, AEAD, hash functions, MAC,
passwords and key derivation, digital signatures, TLS 1.3, the Signal protocol, post-quantum cryptography,
side channels, secret sharing, zero knowledge and computing on encrypted data.

## Running locally

Open `index.html` in a browser. That is all: the pages work from `file://` without a server.

## Publishing on GitHub Pages

Settings → Pages → Build and deployment → Source: "Deploy from a branch", Branch: `main`, folder: `/ (root)`.
All links are relative, so the site works the same from a local folder and from GitHub Pages. The empty file
`.nojekyll` tells GitHub Pages to serve the files as they are.

## Adding a simulator

1. Make a folder next to `index.html`, for example `rc4/`, with the page in `rc4/index.html`. Start from
   `chacha20/index.html`: it has the shared frame (top bar, steps in the sidebar, cards, PL/EN, dark mode,
   the "More below" button, keyboard navigation and `#1`, `#2`, ... links to steps).
2. In `index.html`, fill in `href: "rc4/index.html"` for its topic in the `TOPICS` list, or add a new entry with
   `en` and `pl` texts (`topic`, `name`, `desc`, `chips`) and an icon. Cards appear in the order of the list.
3. In the new page, link back with `href="../index.html"` and keep the language in `localStorage` under the key
   `cryptoSimLang`, so the PL/EN choice is shared by all pages.
4. Keep the cryptography in one plain block marked `CORE-BEGIN` / `CORE-END`, separate from the page code, and
   add a self-test against published test vectors.
5. Avoid very wide elements (over about 4000 px) with a CSS mask or filter that move: Chrome on Linux then fails to
   repaint parts of the page.

The contents pages (`math/`, `pki/`) keep their sections in one array; giving a section an `href` turns it into a
link and removes its "coming soon" badge.

## License

The code is released under the MIT License, see [LICENSE](LICENSE).
