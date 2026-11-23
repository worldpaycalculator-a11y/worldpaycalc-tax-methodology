# 🌍 World Pay Calculator — Open Cross-Border Tax & FX Fee Methodology

[![Live Calculator](https://shields.io)](https://worldpaycalc.com)
[![License: MIT](https://shields.io)](https://opensource.org)

Open documentation of the mathematical formulas, FX spread assumptions, platform fee structures, and simplified effective tax rates powering **[World Pay Calculator](https://worldpaycalc.com)** — a free, privacy-first net-income calculator for freelancers and remote contractors paid by foreign clients.

> **Try the Live Calculator:** [https://worldpaycalc.com](https://worldpaycalc.com)  
> **Corridor Guides:** [https://worldpaycalc.com](https://worldpaycalc.com) | **Full Methodology:** [https://worldpaycalc.com](https://worldpaycalc.com)

---

## 📐 Core Calculation Formulas

### 1. Forward Calculation (Gross Invoice → Net Take-Home Pay)

When a freelancer bills a foreign client a gross amount $G$, three sequential deductions sit between the invoice and spendable local currency:

1. **Platform / Marketplace Fee ($F_{\text{platform}}$):**
   $$F_{\text{platform}} = G \times r_{\text{platform}}$$

2. **FX Conversion & Transfer Cost ($F_{\text{fx}}$):**
   $$F_{\text{fx}} = \big((G - F_{\text{platform}}) \times m_{\text{fx}}\big) + F_{\text{fixed}}$$

3. **Taxable Net Receipts ($R_{\text{taxable}}$):**
   $$R_{\text{taxable}} = G - F_{\text{platform}} - F_{\text{fx}}$$

4. **Estimated Local Income / Self-Employment Tax ($T_{\text{local}}$):**
   $$T_{\text{local}} = R_{\text{taxable}} \times r_{\text{tax}}$$

5. **Final Net Take-Home Pay ($N_{\text{local}}$):**
   $$N_{\text{local}} = (R_{\text{taxable}} - T_{\text{local}}) \times E_{\text{mid}}$$

Where:
* $G$ = Gross invoice in client currency (`USD`, `EUR`, `GBP`, `CAD`, `AUD`)
* $r_{\text{platform}}$ = Marketplace fee rate (e.g., `0%` Direct, `10%` Upwork, `20%` Fiverr)
* $m_{\text{fx}}$ = Provider exchange-rate spread over the live mid-market rate
* $F_{\text{fixed}}$ = Flat wire or withdrawal fee (in client currency)
* $r_{\text{tax}}$ = Simplified effective tax rate (or custom user-defined rate)
* $E_{\text{mid}}$ = Live mid-market exchange rate

---

### 2. Reverse Calculation (Target Net Pay → Required Gross Invoice)

To calculate what gross invoice $G$ a freelancer must charge to keep a target net amount $N_{\text{client}}$ (in client currency) after all fees and taxes, each deduction is compounded inversely rather than simply added:

$$G = \frac{\left(\frac{N_{\text{client}}}{(1 - r_{\text{tax}}) \times (1 - m_{\text{fx}})}\right) + F_{\text{fixed}}}{1 - r_{\text{platform}}}$$

*(Test this reverse formula live using the **"I want a target net pay → Show what I should charge"** toggle on [World Pay Calculator](https://worldpaycalc.com).)*

---

## 💳 Payment Method Fee Assumptions

Baseline fee models used in the [World Pay Calculator comparison engine](https://worldpaycalc.com) (example benchmark on a `$4,000 USD` invoice):

| Payment Method | Platform Fee | Typical FX & Transfer Cost | Notes |
| :--- | :--- | :--- | :--- |
| **Direct Client (Wise)** | `0%` | `~0.6%` (`~$24`) | Closest to live mid-market exchange rate; low transparent transfer fee |
| **Deel** | `0%` *(client-billed)* | `~1.38%` (`~$55`) | Contractor withdrawal & FX conversion spread |
| **Payoneer** | `1%` (`$40` receiving) | `~2.0%` (`~$79.20`) | Standard receiving fee + FX conversion margin to local bank |
| **Direct Bank Wire (SWIFT)** | `0%` | `~$150` (`$25–$40` wire + `~3%` bank FX markup) | Traditional commercial bank SWIFT conversion spread |
| **Upwork** | `10%` (`$400`) | `~1.8%` (`~$72.99`) | 10% freelancer service fee + local bank withdrawal/FX margin |
| **Fiverr** | `20%` | `~1.8%` | 20% marketplace commission + withdrawal conversion spread |

---

## 🌐 Supported Home Countries & Tax Regimes

[World Pay Calculator](https://worldpaycalc.com) supports simplified effective tax modeling and custom tax overrides for 10 major remote-work hubs:

* 🇰🇪 **Kenya** (`KES`) — Local income / turnover tax planning estimates
* 🇳🇬 **Nigeria** (`NGN`) — Personal income tax estimates for remote contractors
* 🇮🇳 **India** (`INR`) — Presumptive taxation under Section 44ADA (`~10%` effective on 50% deemed profit)
* 🇵🇭 **Philippines** (`PHP`) — Graduated vs. 8% flat gross income tax option
* 🇺🇸 **United States** (`USD`) — Federal + self-employment tax planning baseline
* 🇬🇧 **United Kingdom** (`GBP`) — Income tax + Class 4 National Insurance baseline
* 🇨🇦 **Canada** (`CAD`) — Federal/provincial + CPP self-employed baseline
* 🇩🇪 **Germany** (`EUR`) — Freiberufler income tax planning estimate
* 🇧🇷 **Brazil** (`BRL`) — Simples Nacional / MEI contractor baseline
* 🇲🇽 **Mexico** (`MXN`) — RESICO simplified contractor regime baseline

---

## 🔒 Privacy & Disclaimer

* **100% Client-Side Execution:** All calculations on [World Pay Calculator](https://worldpaycalc.com) run locally in the browser—no login is required and no financial inputs are stored on external servers.
* **Disclaimer:** Figures provided in this repository and on [worldpaycalc.com](https://worldpaycalc.com) are planning estimates only and do not constitute formal tax, legal, or financial advice.

---

## 🔗 Links

* **Official Website:** [https://worldpaycalc.com](https://worldpaycalc.com)
* **Contact:** `contact@worldpaycalc.com`
