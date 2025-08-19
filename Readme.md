To use a **virtual environment (venv)** inside **JupyterLab**, you need to:

---

### ✅ 1. Install Jupyter and `ipykernel` inside the venv

Activate your virtual environment:

```bash
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate     # On Windows
```

Then install required packages:

```bash
pip install jupyterlab ipykernel
```

---

### ✅ 2. Add the venv to Jupyter as a new kernel

Run this:

```bash
python -m ipykernel install --user --name=your_venv_name --display-name "Python (your_venv_name)"

python -m ipykernel install --user --name=youtube_poc --display-name "Python (your_venv_name)"

```

* `--name`: internal identifier (no spaces)
* `--display-name`: what you'll see in JupyterLab’s kernel dropdown

Example:

```bash
python -m ipykernel install --user --name=donate-raja-env --display-name "Python (Donate Raja)"
```

---

### ✅ 3. Open JupyterLab

Still inside the venv:

```bash
jupyter lab
```

Then:

* Go to **Launcher → Notebook → Select Kernel → Python (your\_venv\_name)**

---

### 🔁 To remove a kernel later (optional):

```bash
jupyter kernelspec list  # Get installed kernels
jupyter kernelspec uninstall your_venv_name
```

---

Let me know if you want this setup scripted or added to your Makefile or shell script!


Absolutely — here's a **clean, minimal step-by-step guide** to install and configure `pyenv-win` **correctly from scratch**, avoiding all the earlier issues:

---

## ✅ Clean Setup Steps for `pyenv-win` on Windows

### 1. **Install pyenv-win**

Open PowerShell or CMD and run:

```bash
git clone https://github.com/pyenv-win/pyenv-win.git "%USERPROFILE%\.pyenv"
```

---

### 2. **Set Environment Variables**

Open **Start → Environment Variables**, then:

#### Under **User Variables**, add:

- `PYENV = C:\Users\<your-username>\.pyenv\pyenv-win`

#### Edit your **Path** (User scope), add:

```
%PYENV%\bin
%PYENV%\shims
```

✅ Click OK → OK → Restart your terminal.

---

### 3. **Verify pyenv is working**

In a **new terminal**:

```bash
pyenv --version
```

You should see something like: `pyenv 3.x.x`

---

### 4. **Install a Python version**

```bash
pyenv install 3.11.8
```

---

### 5. **Set global version**

```bash
pyenv global 3.11.8
```

---

### 6. **Check version is active**

```bash
python --version
```

Should show: `Python 3.11.8`

---

### 7. **Use in PyCharm**

In **PyCharm**:

- Go to: `File → Settings → Project → Python Interpreter`
- Click ⚙️ → **Add...**
- Choose **System Interpreter**
- Browse to:
  ```
  C:\Users\<your-username>\.pyenv\pyenv-win\versions\3.11.8\python.exe
  ```
- Select it → OK → Apply ✅

---

### ✅ Done!

Let me know if you want a script that automates steps 1–5.