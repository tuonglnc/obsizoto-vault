# 📘 Setup Guide: Zotero & Dataview Obsidian Plugins

This guide will help you set up two essential plugins in Obsidian: **Zotero Integration** (to sync your readings) and **Dataview** (to auto-generate your reading list).

---

## 🔌 1. Setting up Zotero Integration

This plugin automatically pulls paper metadata, abstracts, and highlights from **Zotero** into **Obsidian**.

### Step 1.1: Install Better BibTeX on Zotero (Desktop)
1. Download the Better BibTeX `.xpi` file from GitHub: [Download Better BibTeX](https://github.com/retorquere/zotero-better-bibtex/releases) (choose the latest release).
2. Open Zotero, go to **Tools** -> **Add-ons**.
3. Click the gear icon in the top-right corner -> **Install Add-on From File...** -> Select the `.xpi` file you downloaded -> Restart Zotero.

### Step 1.2: Set Up Zotero Integration in Obsidian
1. In Obsidian, go to **Settings** -> **Community Plugins** -> Click **Browse**.
2. Search for **Zotero Integration** and click **Install**, then click **Enable**.
3. Open Zotero Integration settings (under Community Plugins), scroll down to the **Templates** section -> Click **Add Import Format** and fill in:
   * **Name**: `Import Paper`
   * **Output Path**: Copy and paste this exact formula:
     ```text
     02-Papers/{% if creators | length == 1 %}{{creators[0].lastName}}{% elif creators | length == 2 %}{{creators[0].lastName}} & {{creators[1].lastName}}{% else %}{{creators[0].lastName}} et al.{% endif %} ({{date | format("YYYY")}}) - {{title | truncate(50, true, "") | replace(":", " -") | replace("/", "-") | replace("\\", "-") | replace("?", "")}}.md
     ```
   * **Image Output Path**: `02-Papers/attachments/{{citekey}}/`
   * **Template File**: Click the search box, search for `Zotero-Paper-Template`, and select:
     `00-Templates/Zotero-Paper-Template.md`

---

## 📊 2. Setting up Dataview

This plugin scans your notes and automatically updates your reading list table.

### Step 2.1: Install Dataview in Obsidian
1. In Obsidian, go to **Settings** -> **Community Plugins** -> Click **Browse**.
2. Search for **Dataview** -> Click **Install**, then click **Enable**.

### Step 2.2: Enable Required Settings
Go to Dataview settings (under Community Plugins) and enable:
* **Enable Inline Queries** (allows simple queries directly in text).
* **Enable JavaScript Queries** (allows advanced queries).

---

## 🐙 3. Syncing to GitHub (How to manage Git)

To avoid conflicts between your notes and your code repositories:
1. **Initialize Git at the Root Folder**:
   Open your terminal at the root directory of your Obsidian Vault and run:
   ```bash
   git init
   git add .
   git commit -m "initial commit: research vault notes"
   ```
   *(The `.gitignore` file will automatically ignore the `Projects/` folder so your notes remain clean and light).*
2. **Push to a Private GitHub Repository**:
   Create a Private repository on GitHub, then link and push it:
   ```bash
   git branch -M main
   git remote add origin <YOUR_GITHUB_NOTES_REPO_URL>
   git push -u origin main
   ```
3. **For Coding Projects**:
   Each subfolder inside `Projects/` (e.g. `Projects/Project1/`) is independent. You can initialize a separate Git repository there and push it to a separate repository:
   ```bash
   cd Projects/Project1
   git init
   git add .
   git commit -m "initial commit: code"
   git branch -M main
   git remote add origin <YOUR_GITHUB_CODE_REPO_URL>
   git push -u origin main
   ```
