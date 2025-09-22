# End-to-End Walkthrough: VM Usage Reports

This walkthrough will guide you through generating **daily, weekly, and monthly VM usage reports** for the **eClaims VM**, **eClaims VM v2**, and **STATA VM**.

You do not need to write code — just follow the steps below.

---

## 1. Install Required Software

1. **GitHub Desktop**

   - Download from [https://desktop.github.com](https://desktop.github.com)
   - Install and sign in with your GitHub account.

2. **Visual Studio Code (VS Code)**

   - Download from [https://code.visualstudio.com](https://code.visualstudio.com)
   - During install, check **“Add to PATH”** and **“Open with Code”** options.

3. **VS Code Extensions**
   Open VS Code → Extensions (square icon on left panel) → search and install:

   - **Python** (Microsoft)
   - **Jupyter** (Microsoft)

4. **Python (latest version)**

   - Download from [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)
   - During install, check **“Add Python to PATH”**.

---

## 2. Clone the Repository

1. Open **GitHub Desktop**.
2. Click **File → Clone Repository**.
3. Paste this URL:

   ```
   https://github.com/pids-drg-team/pids-drg-vm-stats
   ```

4. Choose a local folder (e.g., `Documents\GitHub`) and click **Clone**.
5. When finished, click **Open in Visual Studio Code**.

---

## 3. Prepare Input Data

Download **Cloud Logging JSON logs** for each VM:

- **eClaims VM**
  [Download here](https://cloudlogging.app.goo.gl/RbFvX2GVtRrEamaD8) → save as:

  ```
  data/inputs/eclaims.json
  ```

- **eClaims VM v2**
  [Download here](https://cloudlogging.app.goo.gl/ksdz79DERaatzKEp6) → save as:

  ```
  data/inputs/eclaims-v2.json
  ```

- **STATA VM**
  [Download here](https://cloudlogging.app.goo.gl/qfMqdAv79nZ8cmha7) → save as:

  ```
  data/inputs/stata.json
  ```

✅ After saving, your folder should look like this (as in your screenshot):

```
pids-drg-vm-stats/
├── data/
│   └── inputs/
│       ├── eclaims.json
│       ├── eclaims-v2.json
│       └── stata.json
├── image-1.png
├── image-2.png
├── image-3.png
├── main.ipynb
├── README.md
└── requirements.txt
```

---

## 4. Install Dependencies

1. Open VS Code in the `pids-drg-vm-stats` folder.
2. At the top, click **Terminal → New Terminal**.
3. In the terminal, type:

   ```
   pip install -r requirements.txt
   ```

This installs the needed libraries:

- `pandas`
- `matplotlib`

---

## 5. Run the Notebook

1. In VS Code, open **`main.ipynb`**.
2. At the top right, click **Select Kernel** → choose your installed Python.
3. Run all cells:

   - Click **Run All** (play button with “Run All” label), or
   - Press **Shift+Enter** cell by cell.

The notebook will:

- Parse VM logs
- Calculate usage sessions
- Aggregate results (daily, weekly, monthly)
- Generate bar chart visualizations

---

## 6. View Reports

Reports will appear as charts inside VS Code:

- **Daily VM Usage**
- **Weekly VM Usage**
- **Monthly VM Usage**

Each VM (eClaims, eClaims v2, STATA) will have its own set.

---

## 7. Example Output

Daily usage example:

![Daily Usage](image-1.png)

Weekly usage example:

![Weekly Usage](image-2.png)

Monthly usage example:

![Monthly Usage](image-3.png)

---

## 8. Troubleshooting

### ❌ Problem: _No Python kernel found in VS Code_

- Make sure Python is installed from [python.org](https://www.python.org/downloads/windows/).
- Restart VS Code.
- In the top-right of the notebook, click **Select Kernel** → **Python (path/to/python.exe)**.

### ❌ Problem: _pip not recognized_

- During Python installation, ensure **“Add Python to PATH”** was checked.
- If missed, reinstall Python and check it.

### ❌ Problem: _Jupyter not installed_

- In the VS Code terminal, run:

  ```
  pip install jupyter
  ```

### ❌ Problem: _Plots don’t show in VS Code_

- Make sure the **Jupyter extension** is installed in VS Code.
- Restart VS Code and re-run `main.ipynb`.

### ❌ Problem: _JSON files not found_

- Confirm the log files are saved in the correct folder:

  ```
  data/inputs/eclaims.json
  data/inputs/eclaims-v2.json
  data/inputs/stata.json
  ```

---

## 9. Updating Reports

- To refresh reports, replace the old JSON log files in `/data/inputs/` with the latest downloads.
- Re-run **`main.ipynb`**.
