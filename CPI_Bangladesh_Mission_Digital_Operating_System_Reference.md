Now I have everything I need. Let me build the complete interactive system architecture reference. Now let me build the full interactive system architecture:Here is your complete **CPI Bangladesh Mission Digital Operating System** reference — fully grounded in the Employee Handbook, the deep research document, and the CPI hierarchy you provided. Use the six tabs to navigate each component of the system.

---

## CONTEXT

This system mirrors CPI's four-tier hierarchy — **Global HQ → Bangladesh Mission → Cox's Bazar Project Office → Field Sites** — and runs entirely inside Google Workspace, built around your existing Shared Drive `000_BGD_CPMS`.

---

## STRUCTURE

The architecture has three core pillars:

**1. Folder spine** — every level (Mission, Project, Field) has the same numbered subfolder pattern: `00_Templates` (always first), then support units `01_HRA` through `05_MC`, then programs `10_Programs`, then `11_Projects`, and finally `99_Archive` (always last). This means files always sort in the same order everywhere.

**2. Template engine** — the `00_Templates` folder inside every major unit holds the master copies of all forms, sheets, and docs. You never edit a master directly. You make a copy, move it to the working folder, rename it with the correct date and version, and log it in the central `CPI_BGD_TemplateRegistry_Master` sheet. This is your single source of truth for what version of every tool is currently active.

**3. Version control** — file names carry the version number (e.g. `_v1.0`, `_v2.1`). Minor changes increment the decimal. Major restructures increment the whole number. Old versions move to `99_Archive`, never get deleted.

---

## STEP-BY-STEP — WHERE TO START

Follow this sequence to build the system from your existing `000_BGD_CPMS` Shared Drive:

**Step 1 — Create the root folder structure.** Inside `000_BGD_CPMS`, create these folders in order: `00_Templates`, `01_HRA`, `02_G&F`, `03_LSC`, `04_MER`, `05_MC`, `10_Programs`, `11_Projects`, `99_Archive`.

**Step 2 — Build the Programs subfolder.** Inside `10_Programs`, create four folders: `H&N`, `S&D`, `ERP`, `R&L`. Inside `H&N`, create `HOP`, `HPP`, `HSS`. Inside `S&D`, create `WASH`, `CE`, `EDU`, `LIV`.

**Step 3 — Build the Project Office.** Inside `11_Projects`, create `CoxsBazar`. Inside that, mirror the same structure — `00_Templates`, `01_HRA`, `02_G&F`, `03_LSC`, `04_MER`, `05_MC`, `10_Programs` (with the same H&N and S&D subfolders), `ERP`, `R&L`.

**Step 4 — Build Field folders.** Inside the CoxsBazar H&N and WASH folders, create camp-level subfolders: `Camp_01W`, `Camp_04`, `Camp_17`, `Host_Community`, and for HSS: `Sadar_Hospital`, `RTMI_PHCC_Camp05`.

**Step 5 — Create the Template Registry.** In `00_Templates`, create a new Google Sheet named `CPI_BGD_TemplateRegistry_Master_v1.0`. Add the column headers shown in the "Sheet templates" tab above. This becomes your version control ledger.

**Step 6 — Create your first master templates.** Start with the H&N Patient Log sheet and the HOP Patient Intake form, stored in `00_Templates / Sheets` and `00_Templates / Forms` respectively, using the naming convention shown in the "Naming rules" tab.

When you are ready, say **"Build the HOP Patient Intake Form step by step"** or **"Design the MER Indicator Tracker sheet"** and I will give you the exact questions, column headers, and setup instructions for each.

---

## CONTEXT

The **CPI Global HQ** folder is the top of the hierarchy. It holds governance documents, global standards, and master resources that flow **downward** to all country missions — Bangladesh, Myanmar, and Thailand. Nothing operational (daily data, field logs) lives here. Only policy, standards, and approved frameworks.

---

## STRUCTURE

Think of Global HQ as the **"law library"** of CPI. Country missions refer to it, copy from it, but never edit it directly. It has two types of content:

- **Governance layer** — who CPI is, how it operates, legal and financial frameworks
- **Standards layer** — approved templates, SOPs, and reporting formats that all missions must follow

---

## ARTIFACTS

### Exact folder structure inside `CPI_Global_HQ`

```
CPI_Global_HQ/
│
├── 00_Templates/
│   ├── Forms/
│   ├── Sheets/
│   ├── Docs/
│   ├── JSON_Schemas/
│   └── VERSION_LOG  ← Master Template Registry sheet
│
├── 01_Governance/
│   ├── CPI_Global_MissionStatement_v1.0
│   ├── CPI_Global_OrgChart_2026_v1.0
│   ├── CPI_Global_StrategicPlan_v1.0
│   └── CPI_Global_BoardPolicies_v1.0
│
├── 02_Finance/
│   ├── CPI_Global_Finance_Policy_v1.0
│   ├── CPI_Global_BudgetFramework_v1.0
│   ├── CPI_Global_DonorReporting_Template_v1.0
│   └── CPI_Global_AuditReports/
│
├── 03_HR_Admin/
│   ├── CPI_Global_HRPolicy_v1.0
│   ├── CPI_Global_EmployeeHandbook_v1.0  ← your Nov 2025 handbook
│   ├── CPI_Global_CompensationFramework_v1.0
│   └── CPI_Global_SafeguardingPolicy_v1.0
│
├── 04_Logistics/
│   ├── CPI_Global_ProcurementPolicy_v1.0
│   ├── CPI_Global_LSC_SOP_v1.0
│   └── CPI_Global_AssetManagement_v1.0
│
├── 05_Programs/
│   ├── H&N/
│   │   ├── CPI_Global_HN_Framework_v1.0
│   │   └── CPI_Global_HN_IndicatorGuide_v1.0
│   ├── S&D/
│   │   ├── CPI_Global_SD_Framework_v1.0
│   │   └── CPI_Global_SD_IndicatorGuide_v1.0
│   ├── ERP/
│   │   └── CPI_Global_ERP_Framework_v1.0
│   └── R&L/
│       └── CPI_Global_RL_ResearchPolicy_v1.0
│
├── 06_MER/
│   ├── CPI_Global_MEL_Framework_v1.0
│   ├── CPI_Global_IndicatorDictionary_v1.0
│   └── CPI_Global_ReportingCalendar_2026_v1.0
│
├── 07_Partnerships/
│   ├── CPI_Global_PartnershipPolicy_v1.0
│   ├── CPI_Global_SubgrantManagement_SOP_v1.0
│   └── Partner_Agreements/  ← signed MoUs, sub-grant agreements
│
├── 08_Communications/
│   ├── CPI_Global_BrandGuidelines_v1.0
│   ├── CPI_Global_CommunicationsPolicy_v1.0
│   └── CPI_Global_MediaKit/
│
└── 99_Archive/
    └── [retired versions of any of the above]
```

---

### File naming convention for Global HQ

| Pattern | Example |
|---|---|
| `CPI_Global_[Unit]_[DocType]_[Name]_v[X.Y]` | `CPI_Global_Finance_Policy_BudgetFramework_v1.0` |
| `CPI_Global_[Program]_[DocType]_[Name]_v[X.Y]` | `CPI_Global_HN_Framework_IndicatorGuide_v2.0` |

---

### What each folder holds — plain language

| Folder | What goes in it | Who uses it |
|---|---|---|
| `00_Templates` | Master blank forms, sheet templates, SOP templates — copy from here, never edit here | All country missions |
| `01_Governance` | Org chart, strategic plan, board policies, mission statement | SMT, Country Representatives |
| `02_Finance` | Global finance policy, donor reporting requirements, audit reports | G&F teams globally |
| `03_HR_Admin` | Global HR handbook, safeguarding policy, compensation framework | HRA globally |
| `04_Logistics` | Global procurement rules, asset management policy | LSC globally |
| `05_Programs` | Program frameworks and indicator guides for H&N, S&D, ERP, R&L | Program Managers globally |
| `06_MER` | Global MEL framework, indicator dictionary, reporting calendar | MER globally |
| `07_Partnerships` | Partnership policy, sub-grant SOP, signed MoUs | CR, G&F, Program leads |
| `08_Communications` | Brand guidelines, communications policy, media kit | M&C globally |
| `99_Archive` | Old versions of any document — never deleted, just retired here | Admins only |

---

## STEP-BY-STEP

Here is exactly how to build this in Google Drive:

**Step 1 — Create the root folder.** In your Google Drive (or inside a shared Team Drive), click **New → Folder** and name it exactly: `CPI_Global_HQ`. Share it with HQ admins and Country Representatives as Editors. Share it with all Bangladesh mission staff as **Viewers** only.

**Step 2 — Create the eight subfolders.** Open `CPI_Global_HQ`, then click **New → Folder** eight times, naming each one: `00_Templates`, `01_Governance`, `02_Finance`, `03_HR_Admin`, `04_Logistics`, `05_Programs`, `06_MER`, `07_Partnerships`, `08_Communications`, `99_Archive`.

**Step 3 — Build the Programs subfolder.** Open `05_Programs` and create four subfolders inside: `H&N`, `S&D`, `ERP`, `R&L`.

**Step 4 — Build the Templates subfolder.** Open `00_Templates` and create: `Forms`, `Sheets`, `Docs`, `JSON_Schemas`. Then create a new Google Sheet inside it named `CPI_Global_TemplateRegistry_Master_v1.0`.

**Step 5 — Upload your first documents.** Start with what you already have — the Employee Handbook belongs in `03_HR_Admin`, named `CPI_Global_HRA_Doc_EmployeeHandbook_2026-01_v1.0`. The CPI org chart PDF belongs in `01_Governance`, named `CPI_Global_GOV_OrgChart_HQ_2026-03_v1.0`.

**Step 6 — Set permissions correctly.** Right-click each subfolder and set sharing so that only the relevant team can edit. For example, `02_Finance` should be editable only by G&F staff — all others get View access. The `00_Templates` folder should be **View only for everyone** except the system admin who manages master files.

**Step 7 — Link Global HQ to Bangladesh.** In your `000_BGD_CPMS` Shared Drive, create a Google Doc named `CPI_BGD_GlobalHQ_ResourceLinks_v1.0` stored in your `00_Templates` folder. Inside it, paste direct Drive links to the key Global HQ documents Bangladesh teams need to reference (HR policy, MEL framework, brand guidelines). This way Bangladesh staff never need to navigate the Global HQ folder structure — they get the links they need from one place.

---

When you are ready, say **"Now build the Bangladesh Mission 000_BGD_CPMS folder structure in detail"** and I will give you the same level of detail for every subfolder specific to the Bangladesh operation.

---
Here is your complete **000_BGD_CPMS** blueprint — six tabs covering every dimension of the system.

---

## CONTEXT

The `000_BGD_CPMS` Shared Drive is the **operational nerve centre** of the Bangladesh Mission. Unlike the Global HQ folder (which holds governance and standards), this drive holds everything that is *actively used* day to day — from field patient logs in Camp 01 West to the Finance Manager's budget tracker in Dhaka. It has three distinct layers inside it: the **Mission layer** (support units 01–05 and program frameworks in 10_Programs), the **Project layer** (Cox's Bazar inside 11_Projects), and the **Field layer** (camp-by-camp subfolders inside each program).

---

## KEY DESIGN DECISIONS — WHY THIS STRUCTURE

Three things are worth understanding before you start building:

The `00_Templates` folder comes first and is the most important folder in the entire drive. Every other folder draws from it. If you skip building this first, you will end up with inconsistent files scattered across the drive with no version control. Build it before anything else.

The Cox's Bazar Project Office (`11_Projects/CoxsBazar`) is a **mirror** of the mission structure — it has its own support unit folders (`01_HRA` through `05_MC`) because the Cox's Bazar team manages its own HR, finance, and logistics independently from Dhaka, even though they report upward. This is intentional and reflects how CPI operates in practice.

The `Partners/` folder inside CoxsBazar is separate from the program folders. Partner documents (YPSA sub-grant agreement, Educo MoU, RTMI reports) are stored there — not mixed into the H&N or S&D program folders. This keeps partner accountability documents in one place and makes partner reviews straightforward.

---

## NEXT STEPS

Use the **Build sequence** tab as your day-one checklist. Work through all 10 steps in order. Steps 1–5 should take roughly two hours to complete for the folder structure alone.

When you are ready to go deeper, say any of these:

- **"Build the HOP Patient Daily Log form step by step"** — and I will give you every form question, field type, and dropdown option
- **"Design the MER Indicator Tracker sheet in full"** — column headers, data validation rules, and how to connect it to Looker Studio
- **"Set up the TemplateRegistry Master sheet"** — exact columns, dropdown validations, and how to log your first three templates

---


Let me read the skill file and understand the Colab notebook context first.Good. Now let me understand exactly what the user needs — they want a Google Colab notebook (`.ipynb`) that will **automatically create the entire folder + file structure** inside their Google Drive Shared Drive `000_BGD_CPMS` using the Google Drive API. Let me build this properly.Your Colab notebook is ready to download. Here is exactly what it does and how to use it.

---

## CONTEXT

This notebook uses the **Google Drive API v3** and **Google Sheets API v4** — both free and built into Colab — to automatically create the entire `000_BGD_CPMS` folder structure without you having to click anything manually. It is safe to re-run at any time: it checks whether each item already exists before creating it, so nothing gets duplicated.

---

## WHAT THE NOTEBOOK BUILDS (10 steps)

| Step | What it does |
|---|---|
| 1 | Installs Drive and Sheets API libraries |
| 2 | Authenticates with your `ariful@cpintl.org` account |
| 3 | Loads all helper functions (create folder, sheet, doc, JSON) |
| 4 | Builds all **folders and subfolders** across all 4 tiers |
| 5 | Creates **20 master Google Sheets** in `00_Templates/Sheets` |
| 6 | Creates **21 master Google Docs** in `00_Templates/Docs` |
| 7 | Creates **7 JSON schema files** in `00_Templates/JSON_Schemas` |
| 8 | Populates the **Template Registry** master index sheet with all 20 rows |
| 9 | Prints a full summary report with counts and links |
| 10 | Writes correct **column headers** into every master Sheet |

---

## STEP-BY-STEP: How to run it

**Step 1 — Upload the notebook to your Colab.**
Open the URL `https://colab.research.google.com/drive/1OfMgOWUGEg3y7vf6bq4gtlRcL7LSG8oE` (your existing blank Colab inside `000_BGD_CPMS`). In Colab, go to **File → Upload notebook** and upload the `.ipynb` file you just downloaded. Or use **File → Open notebook → Upload** tab.

**Step 2 — Check you are signed in as `ariful@cpintl.org`.**
In Colab's top-right corner, confirm the Google account. If it shows a different account, click it and switch.

**Step 3 — Run cells top to bottom.**
Click **Runtime → Run all** or press `Ctrl+F9`. When Cell 2 (Authentication) runs, a popup will ask you to allow Google Drive access — click **Allow**.

**Step 4 — Watch the output.**
Each cell prints what it created or skipped. Folders show `📁 [CREATED]`, sheets show `📊 [CREATED]`, docs show `📄 [CREATED]`. Items that already exist show `[EXISTS]` and are safely skipped.

**Step 5 — Check your Drive.**
When Step 9 finishes, it prints a direct link to your `000_BGD_CPMS` Shared Drive and to the Template Registry sheet. Open both to confirm everything is in place.

---

## ONE IMPORTANT NOTE

The notebook uses your `SHARED_DRIVE_ID = "18N_9Eq4oOCPZoTBW4CbsVNqLVBkvb6KW"` — extracted directly from the Drive URL you provided. If that ID ever changes, update only the `CONFIGURATION` cell (Step 2) and re-run.

---

When the build is complete, say **"Now set up the column headers and data validation for the HOP Daily Patient Log sheet"** and I will walk you through adding dropdowns, conditional formatting, and linking it to a Google Form for field staff.

---

Let me read both files thoroughly.Excellent. I now have the complete picture. Let me synthesize my analysis of both resources.Here is a full analysis of both resources — the executed notebook and the INDEX sheet.

---

## WHAT THE ANALYSIS CONFIRMS

The build is a genuine success. Your notebook ran through 14 steps, created and verified **99 folders**, wrote **19 master Google Sheets with column headers**, created **21 Google Docs**, uploaded **7 JSON schema files**, populated the **Template Registry with 20 rows**, and auto-generated **98 README docs** across every folder. The only error was a single network timeout on one README (R&L subfolder), which was caught and fixed in the same session.

The INDEX sheet quota error is not a build failure — it is a temporary Google API rate limit that resets within 60 seconds. Your INDEX sheet (ID `1jq5y9rY5-WaTtukok7Sol0px5SM5fUG6tF3MQmvBJaQ`) is intact.

---

## THE ONE STRUCTURAL ISSUE TO FIX

When you added Steps 11–14 live, the Global Governance folders (`01_Governance`, `02_Finance`, `03_HR_Admin`…) were created at the same root level as the Bangladesh Mission support unit folders (`01_HRA`, `02_G&F`…). Both sets start with `01_`, `02_`, `03_` — so in Google Drive they will sort into each other and look like one confused set of folders. This is the only design issue worth fixing before you move forward.

---

## IMMEDIATE ACTION — DO THIS NOW

Your Colab session is still active. Before it expires, go to the Colab left panel (click the folder icon), find these three files, and download them to your computer: `CPI_BGD_Folder_Registry.csv`, `CPI_BGD_Mission_OS_Folder_Registry.xlsx`, and `CPI_BGD_OS_Build_Summary.json`. They disappear when the session ends.

---

## WHAT TO ASK NEXT

Say any of these to continue building:

- **"Write the Colab cell to fix the Global folder naming conflict"** — renames the 8 Step-11 folders with a `GBL_` prefix
- **"Write the Colab cell to upload the registry files to Drive"** — saves CSV/Excel/JSON permanently into `00_Templates/`
- **"Write the Colab cell to populate the INDEX sheet with all 99 folder IDs and Drive URLs"** — turns the INDEX into your master navigation map
- **"Write the Colab cell to create Google Forms from the JSON schemas"** — builds the 7 data collection forms using the Forms API
