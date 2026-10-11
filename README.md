# Toolbay — The Digital Atelier of Precision Online Tools & Calculators

[![Live Production Site](https://img.shields.io/badge/Live%20Site-tools.xyzhome.site-EF6F79?style=for-the-badge&logo=googlechrome&logoColor=white)](https://tools.xyzhome.site/)
[![License: MIT](https://img.shields.io/badge/License-MIT-slate.svg?style=for-the-badge)](LICENSE)
[![Architecture: 100% Client-Side](https://img.shields.io/badge/Architecture-100%25%20In--Browser-success?style=for-the-badge)](#architecture)

> **Live Web Application:** [https://tools.xyzhome.site](https://tools.xyzhome.site/)

**Toolbay** is an open-access, zero-telemetry suite of 16 high-precision mathematical calculators, financial engineering tools, unit converters, and developer utilities. Engineered with a strict zero-knowledge paradigm, every algorithm, cryptographic string, and raster image operation runs 100% inside your local browser sandbox via the HTML5 Canvas API, Web Cryptography API, and strict IEEE-754 arithmetic.

---

## 🧰 Featured Precision Instruments

All instruments are fully functional offline with zero server round-trips:

| # | Instrument | Category | Direct Link | Key Capability |
|---|---|---|---|---|
| 01 | **Age Calculator** | Chronology | [Launch Tool](https://tools.xyzhome.site/tools/age-calculator) | Exact age breakdown, leap-year correction & birthday countdown |
| 02 | **Date Difference Calculator** | Calendar | [Launch Tool](https://tools.xyzhome.site/tools/date-difference-calculator) | Calendar spans, working business days & weekend calculations |
| 03 | **Percentage Calculator** | Ratio | [Launch Tool](https://tools.xyzhome.site/tools/percentage-calculator) | Three-way percentage share, markup, and relative variance |
| 04 | **Loan EMI Calculator** | Fiscal | [Launch Tool](https://tools.xyzhome.site/tools/loan-emi-calculator) | Reducing-balance compound interest with complete amortization schedules |
| 05 | **Discount Calculator** | Commerce | [Launch Tool](https://tools.xyzhome.site/tools/discount-calculator) | Net price calculation with stacked multi-tier promotional discounts |
| 06 | **Sales Tax Calculator** | Statutory | [Launch Tool](https://tools.xyzhome.site/tools/sales-tax-calculator) | Bidirectional VAT/GST addition and subtraction |
| 07 | **Unit Converter** | Metric | [Launch Tool](https://tools.xyzhome.site/tools/unit-converter) | 8 conversion domains including length, mass, and regional land metrics |
| 08 | **BMI Calculator** | Biometric | [Launch Tool](https://tools.xyzhome.site/tools/bmi-calculator) | WHO clinical classification standard across Metric and Imperial |
| 09 | **Word Counter** | Prose | [Launch Tool](https://tools.xyzhome.site/tools/word-counter) | Real-time character counts, reading velocity & keyword density |
| 10 | **Text Case Converter** | Glyphs | [Launch Tool](https://tools.xyzhome.site/tools/case-converter) | 10 typography transforms (camelCase, snake_case, kebab-case, etc.) |
| 11 | **Password Generator** | Security | [Launch Tool](https://tools.xyzhome.site/tools/password-generator) | Cryptographically secure offline entropy with CSPRNG |
| 12 | **QR Code Generator** | Matrix | [Launch Tool](https://tools.xyzhome.site/tools/qr-code-generator) | Permanent static vector codes for URLs, WiFi, and contact data |
| 13 | **Image Compressor** | Raster | [Launch Tool](https://tools.xyzhome.site/tools/image-compressor) | In-browser lossless and lossy WebP, PNG, and JPG reduction |
| 14 | **JSON Formatter** | Syntax | [Launch Tool](https://tools.xyzhome.site/tools/json-formatter) | Syntax validation, minification, and line-error pointer |
| 15 | **Color Converter** | Chromatics | [Launch Tool](https://tools.xyzhome.site/tools/color-converter) | HEX, RGB, and HSL conversions with WCAG 2.1 contrast evaluation |
| 16 | **D&D 5e Hit Point Calculator** | Metrology | [Launch Tool](https://tools.xyzhome.site/tools/hp-calculator) | Character progression, multiclass hit dice, and Constitution bonuses |

---

## ⚡ Core Architecture

- **Zero Server Latency:** Direct client-side JavaScript execution with synchronous responses at 60–120 FPS.
- **Privacy-First (Zero Data Transmission):** No analytics payloads, no server tracking, and no external database storage.
- **Offline Resilience:** Fully operational offline once cached by the browser service worker.
- **Lightweight Footprint:** Clean semantic HTML5, zero heavy external frameworks, and minimal CSS overhead (~8 KB).

---

## 🚀 Deployment & Local Preview

Clone the repository and inspect locally:

```bash
git clone [https://github.com/](https://github.com/)<your-username>/toolbay-web-tools.git
cd toolbay-web-tools
