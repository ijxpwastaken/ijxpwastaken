# Hello, I'm Jonas 👋

Welcome to my GitHub profile. I'm an engineer with a passion for systems programming and modern web standards.  One of my current challenges is **Scarach Browser**, a web browser built completely from scratch in Rust.  Instead of forking an existing engine, Scarach implements the entire browser stack – network protocols, HTML parser, CSS engine, JavaScript runtime, layout and rendering – as an original codebase, prioritizing security, performance and modern standards compliance【691170807291134†L29-L38】.

## 🌍 About Scarach Browser

Scarach aims to incrementally support the features developers need to build modern web apps while maintaining a clear architecture and strong security posture【691170807291134†L5-L24】.  Here's a snapshot of what this project already includes:

- **Custom network stack** – HTTP/HTTPS client with redirect handling, TLS 1.3 via `rustls`, and certificate validation【691170807291134†L17-L22】.  Future roadmap items include HTTP/2 and WebSocket support【876757230238440†L14-L23】.
- **HTML5 parser and DOM tree** – a forgiving HTML parser with error recovery, quirks‑mode detection and semantic tag support【876757230238440†L24-L32】.  It constructs a complete DOM tree for each loaded page【691170807291134†L18-L21】.
- **CSS engine** – full support for modern layout features, including Flexbox and CSS Grid, variables, animations and cascade handling【691170807291134†L33-L37】.  The engine performs selector matching, specificity calculations and style inheritance【876757230238440†L33-L47】.
- **JavaScript runtime** – a custom JS engine with DOM bindings and compatibility shims for web APIs【691170807291134†L24-L37】.  While page‑level execution is still being wired into navigation, the underlying runtime already supports ES2020 features and garbage collection【876757230238440†L48-L57】.
- **Rendering and layout** – a layout engine computes boxes, positioning and stacking contexts; a renderer built on `winit` and `softbuffer` paints text, images and SVG content【691170807291134†L29-L38】.  Scarach defaults to dark‑mode styling and decodes common image formats (PNG/JPEG/GIF/WebP/BMP)【691170807291134†L19-L22】.
- **Storage and other modules** – persistent storage via localStorage/sessionStorage, cookie management, and cache modules【691170807291134†L37-L37】.  Optional modules provide JIT compilation, crypto primitives, SVG and WebGL support【691170807291134†L38-L38】.

The architecture emphasizes robustness over features; for instance, memory safety is enforced through Rust’s ownership model, and TLS validation helps guard against MITM attacks【876757230238440†L1-L11】.

## 🚀 Running Scarach

If you'd like to try Scarach locally, you'll need the Rust toolchain (1.75 or newer).  Clone the repository and run the following commands:

```bash
# build the project
cargo build --release

# run the browser (defaults to http://google.com and handles the redirect to HTTPS)
cargo run

# development helpers
cargo check       # type‑check only
cargo test        # run tests
cargo fmt         # format code
# lint (requires clippy)
cargo clippy --all-targets --all-features
```

On startup, Scarach opens a native desktop window (`1280×800`) titled “Scarach Browser” and navigates to Google.  Keyboard shortcuts include `Ctrl+L` to focus the address bar, `Ctrl+T` for a new tab, `Ctrl+W` to close a tab and `F5` to reload【691170807291134†L59-L87】.

## 📂 Project Layout

The codebase is organized into modular components:

| Directory | Purpose |
|---|---|
| `src/network/` | TLS 1.3 connector, HTTP client, certificate validation, redirect handling【876757230238440†L14-L23】 |
| `src/html/` | HTML5 parser, tokenizer and DOM tree builder【876757230238440†L24-L32】 |
| `src/css/` | CSS parser, cascade engine, Flexbox and Grid implementations【876757230238440†L33-L47】 |
| `src/js/` | JavaScript engine wrapper with DOM bindings and event system【876757230238440†L48-L57】 |
| `src/layout/` | Layout computation and box model【876757230238440†L58-L65】 |
| `src/render/` | Renderer, canvas API, text and image painting【876757230238440†L66-L74】 |
| `src/storage/` | Local/session storage, cookies and caching【691170807291134†L37-L38】 |
| Additional modules | SVG, crypto, JIT compiler, Tailwind, WebGL and more【876757230238440†L76-L114】 |

Check out `ARCHITECTURE.md` for an in‑depth walkthrough of each subsystem.

## 📈 Roadmap

Scarach is under active development; upcoming milestones include WebAssembly support, GPU rendering with wgpu, service workers, WebRTC and developer tools【876757230238440†L169-L176】.  Contributions and feedback are welcome—feel free to open an issue or pull request on the [Browser repository](https://github.com/ijxpwastaken/Browser).

## 💬 Get in touch

I'm excited about building web infrastructure and exploring low‑level systems programming.  If you'd like to discuss Scarach or collaborate on similar projects, please [reach out via GitHub](https://github.com/ijxpwastaken) or open an issue in the repository.

Thanks for stopping by!
