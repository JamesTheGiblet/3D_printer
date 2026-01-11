# 🛠️ BuddAI | 3D Printing Forensic Diagnostic Engine

BuddAI is a high-performance, rule-based expert system designed to diagnose complex 3D printing failures. It utilizes a massive knowledge base of **1,600+ technical rules** spanning firmware configuration, hardware mechanics, and advanced mechatronics.

## 🚀 Key Features

* **Massive Knowledge Base:** Over 1,600 technical rules derived from real-world 3D printing forensics and engineering.
* **Asynchronous Chunk Parsing:** Optimized for scale; the engine parses thousands of lines without freezing the browser UI via `requestAnimationFrame` logic.
* **Weighted Search Engine:** A specialized scoring algorithm that prioritizes "Symptom" matches over "Note" text to ensure high-relevance results.
* **G-Code & #Define Extraction:** Automatically detects and highlights technical commands and firmware directives in a dedicated code-snippet view.
* **Zero-Dependency Architecture:** Pure HTML5/JavaScript; no heavy frameworks, making it ideal for offline workshop use.

## 📂 Knowledge Base Coverage

The engine provides deep-dive troubleshooting for:
* **Firmware Mastery:** Deep configuration rules for **Marlin 2.1+**, **Klipper**, and **Duet3D (RRF)**.
* **Hardware Forensics:** Specific failure modes for the **Creality K1/V3 series** and industrial printers.
* **Extrusion Ecosystems:** Specialized diagnosis for **E3D Revo**, **Hemera**, and High-Flow systems.
* **Advanced Mechatronics:** Signal integrity, CAN-Bus forensics, and AI-orchestrated monitoring.
* **Material Science:** 50+ rules covering the physics of PLA, PETG, ABS, Nylon-CF, and high-performance polymers.

## 🛠️ Technical Implementation

### Parsing Logic
To handle 1,600+ rules (approx. 5,000+ lines of text) without browser lockup, the engine uses **Non-Blocking Asynchronous Parsing**.
* Data is processed in **16ms bursts**.
* Maintains a smooth **60fps** experience during database initialization.

### Scoring Algorithm
Matches are calculated using a weighted relevance system:
1.  **Exact Phrase Match (Problem):** 10 points.
2.  **Keyword Match (Problem):** 5 points.
3.  **Contextual Match (Explanation):** 2 points.

## 📝 Syntax Guide
The engine parses rules based on a specific forensic syntax. To add to the database, follow this format:

```text
# SECTION: Category Name
/teach Symptom or Problem: The Solution or Fix
/explain Detailed technical justification or step-by-step procedure.
