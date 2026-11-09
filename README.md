# SecureKey
[![Live Demo](https://img.shields.io/badge/Live--Demo-Click%20Here-brightgreen?style=for-the-badge&logo=githubpages)](https://dashkmge.github.io/SecureKey/)

Password generator and strength checker. One static page built with HTML, CSS and vanilla JavaScript. No backend, no build step, no dependencies, no external requests.

The interface blends a near-black, minimalist SaaS look with glassmorphism: translucent blurred panels, a soft spotlight and grid, and restrained cyan, blue and violet accents.

## Features

- **Generator**: length from 8 to 64 (default 20), uppercase, lowercase, numbers, symbols. The password regenerates live as settings change, with a short "decode" reveal animation.
- **Strength indicator**: four levels (Weak, Fair, Strong, Very strong) with an entropy estimate based on length and character pool.
- **Copy to clipboard**: animated success state and toast. Uses the Clipboard API with a fallback, and only reports success when copying actually worked.
- **Strength checker**: analyzes any password for length, variety, common words, keyboard runs, sequences, repeats and years, and gives specific suggestions. It is an estimate, not a guarantee.
- **Accessible**: keyboard navigable, visible focus states, labelled controls, live regions for status, reduced-motion support. Press `G` to generate.
- **Responsive**: layout, type scale and controls are adapted for desktop, tablet and mobile.

## Security and privacy

- Randomness comes from `crypto.getRandomValues()` with rejection sampling (no modulo bias). `Math.random()` is never used.
- Every selected character type is guaranteed to appear, then the result is shuffled with a Fisher-Yates algorithm driven by secure random numbers.
- Everything runs locally. Passwords are never sent anywhere, never logged, and never written to localStorage, sessionStorage, cookies or IndexedDB.
- Invalid configurations (no character type selected) are handled with a clear message and disabled copy.

No tool can guarantee absolute security. Use a unique password per account and enable two-factor authentication.
