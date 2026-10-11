# Autopsy Examination Workflow

## 1. Case Setup

- Create a new case in Autopsy with a unique case name and number
- Set the base directory to a dedicated work folder
- Enter examiner name for chain-of-custody documentation

## 2. Adding the Data Source

- Select **"Disk Image or VM file"** as the source type
- Browse to the forensic image (`.E01`, `.001`, `.dd`)
- Configure ingest modules — either defaults or **Select All** depending on scope

## 3. Ingest Modules

Common modules used:

| Module | Purpose |
|---|---|
| File Type Identification | Categorises files by extension and MIME type |
| Extension Mismatch Detector | Flags files whose content doesn't match extension |
| Keyword Search | Indexes content for text searching |
| Email Parser | Extracts email messages and attachments |
| EXIF Parser | Extracts camera metadata from images |
| Hash Lookup | Identifies known files |
| Recent Activity | Extracts user activity artifacts |
| Timeline | Builds chronological event view |

## 4. Examination Techniques

### File Browsing
- **Views → File Types → By Extension** — browse by category
- **Views → Deleted Files** — locate deleted items
- **Views → File Types → By Extension → Images** — review photos

### Keyword Searching
- Use the **Keyword Search** button in the toolbar
- Choose match type: exact, substring, or regex
- Enable **"Include unallocated space"** for deleted content

### Metadata Analysis
- Select a file → **Content Viewer → File Metadata**
- Record: Created, Modified, Accessed, Changed timestamps
- Note MD5 hash for integrity verification

### Deleted File Recovery
- Navigate to **Views → Deleted Files**
- Check unallocated space via `$Unalloc` folder
- Document **cluster numbers** for hits in unallocated space

## 5. Tagging Evidence

1. Select relevant files in the Result Viewer
2. Right-click → **Tag File → Tag and Comment**
3. Create a descriptive tag name (e.g., "Confidential Documents")
4. Add a comment explaining relevance

## 6. Report Generation

1. Click **Generate Report** in the toolbar
2. Select report module (**Results - Excel** or **HTML**)
3. Choose **Tagged Results** and select your tags
4. Export and organise into the required tab structure
