# Metals Hub – Safe Custody & Physical Portfolio Guide
**Version 0.0.2**

Metals Hub is a local-first secure custody and physical specimen ledger. It is designed to track fine weight calculations, real-time spot benchmark valuations, escrow dispatches, and secure storage mappings.

This guide provides an overview of the core concepts, detailed walkthroughs of each section, active offline directory paths, and configuration procedures.

---

## 1. What is What? (Core Concepts Explained)

To manage precious raw/slabbed physical specimens professionally, it is helpful to understand the underlying parameters tracked in Metals Hub:

*   **Gross Weight vs. Net Fine Weight (Actual Metal Weight in Ounces)**
    *   **Gross Weight:** The entire physical weight of the item (including copper alloys, capsule material, or casing in case of some items).
    *   **Net Fine Weight (oz / toz):** The actual weight of 100% pure metal inside the item. It is automatically converted and measured in Troy Ounces (`toz`) for direct spot rate valuation. For example, a coin with 22-karat gold (91.67% purity) weighing 1.09 Troy Ounces has exactly `1.09 * 0.9167 = 1.00 Troy Ounce` of net fine metal weight.
*   **Purity (Fineness)**
    *   Indicates the percentage of the precious metal in the alloy (e.g., `999.9` for premium investment-grade gold bars, `.999` for bullion, or `.900` for pre-1933 gold coins).
*   **Slabbed vs. Raw Assay**
    *   **Raw / Assay Sealed:** Bulllion items sealed directly by refineries (Valcambi, Perth Mint, PAMP) in tamper-evident plastic cards indicating serial number, assayer name, and certificate number.
    *   **Slabbed:** Specimen coins professionally certified and permanently sealed in hardshell plastic "slabs" by recognized coin grading services such as **PCGS** (Professional Coin Grading Service) or **NGC** (Numismatic Guaranty Company) with a specific numerical grade (ranging from 1 to 70).
*   **Escrow & Multi-Sig (Multi-Signature Validation)**
    *   A custody safeguard for high-value dispatch actions. When an item is sold with "Multi-Sig Escrow Enabled," it enters the **Pending** stage and requires signatures (authorization confirmations) from both buyer and carrier, along with a secure **Verification Code** before it is fully unlocked and marked as **Sold**.
*   **Spot Price Benchmark**
    *   The raw market-clearing rate of the metals (Gold, Silver, Platinum) per Troy Ounce. This benchmark updates instantly upon user refresh triggers, resetting current asset valuations dynamically.

---

## 2. Directory Configuration & Offline Mappings

Metals Hub uses a dual-engine architecture:
1. **Interactive State Ledger (Standard Runtime):** Operates on high-speed browser-local storage for direct offline caching.
2. **Electron Native Database Bridge (Desktop Mode):** Syncs physical state directly to a persistent local JSON schema in secure folder structures.

### Active App Data Storage Directory Mappings
When deployed with Electron, application data is read-written at these paths:

| Operating System | Default App Data File Location |
| :--- | :--- |
| **Windows** | `%APPDATA%\metals-hub\storage.json`<br>*(Typically `C:\Users\<YourUsername>\AppData\Roaming\metals-hub\storage.json`)* |
| **Linux** | `~/.config/metals-hub/storage.json`<br>*(Typically `/home/<yourusername>/.config/metals-hub/storage.json`)* |
| **macOS** | `~/Library/Application Support/metals-hub/storage.json` |

### Active Ledger Configuration File Export Paths
When exporting premium ledger records, CSV archives are written to your customized active configuration location.
You can adjust this target path inside the **Settings** view:
*   **Default Export Directory:** `/var/secure/vault_reserve/backups`
*   **Active Export Filename:** `[Chosen Directory]/ledger_export.csv` (e.g. `C:\YourExportDirectory\ledger_export.csv` or `/user/home/ledger_export.csv`).

---

## 3. Walkthrough: Segment-by-Segment Functions

### 📊 Dashboard View
*   **Portfolio Value Statistics:** Computes total raw fine metal value against live market benchmarks, tracking dynamic yield return/premium on raw cost.
*   **Discreet Status Grid:** Offers abstract graphite hexagon status metrics indicating network latency, custody indexes, and encrypted cluster integrity silently without drawing third-party eye attention to high-value coins or metals.
*   **Weight Chart Distribution:** Visualizes the portfolio allocation ratio across Gold, Silver, and Platinum dynamically.
*   **Recent Activity Log:** Feeds chronological cryptographic action tracking (registrations, removals, trade states, escrow updates) in a high-contrast mono log console.

### 🗄️ Inventory Ledger View
*   **Tabular Collection View:** Lists all assets currently held in collection with comprehensive parameters.
*   **Specimen Inspections:** Clicking on any row opens a deep details slide-out drawer containing serial numbers, assayer details, grading certifications (slab certificates), grade categories, origin country, dimensions, and personal vault notes.
*   **Search & Filters:** Search instantly across serial keys, mints, and tags. Filter specimens by metal types (Gold, Silver, Platinum), purity classes, and condition tiers.

### 🏷️ On Sale (Listing Engine) View
*   **Listing Dispatches:** Select an item from your vault inventory, set its listing price, and dispatch it to sale-pending status.
*   **Markdown Generator:** Automatically formats a ready-to-copy Markdown post compatible with community marketplaces such as Reddit's **r/Pmsforsale**. Includes tabular item specifics, purities, requested payment sources, verification proofs, and shipping methods automatically.

### ⏳ Pending & Escrow Verification View
*   **Transits & Verifications:** Displays items currently undergoing buyer delivery verification or transaction clearance.
*   **Escrow Release Multi-Sig Controller:** Provides the user with interface logs to register multi-signature carrier approvals (`[CARRIER_OK]`, `[BUYER_OK]`) and type in the cryptographic verification passcode to permanently finalize premium payout records.

### 💰 Sold Items Ledger View
*   **Archive Ledger:** Keeps standard transaction history records showing exact sold date, buyer entities, realized prices, selling fees, and net profit/loss (P&L) margins.
*   **Stat Summaries:** Tallies gross sales, historical acquisition costs, total service/broker fees paid out, and total net gains.

### ➕ Add Asset View
*   **Single Asset Form:** A comprehensive input form allowing precise registration of new physical acquisitions. It features automatic net fine metal weight calculations upon weight/unit change.
*   **Bulk CSV Upload Engine:** Lets you process dozens of physical assets simultaneously. Allows you to download standard template column files, paste in values, and drop the CSV directly into the intake engine with structural layout checks.

### ⚙️ Settings View
*   **Security & Encryption Management:** Toggle encryption state protocols for local storage, change secure backup passwords, and manage path keys.
*   **System Action Hooks:** Clean-wipe local datasets, reset standard configurations back to default seed templates, or update active manual benchmark pricing variables.
