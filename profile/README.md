# Welcome to the ERAU TPMS Research Group

This organization hosts our shared C++ geometry generators, OpenFOAM simulation templates, and post-processing workflows for Triply Periodic Minimal Surface (TPMS) research.

---

## 1. First-Time Computer & SSH Setup (New Members Start Here)

If you have never used Git or GitHub before, run these commands in your terminal **once** on each computer you use to link it to your GitHub account.

### Step 1: Set your name and ERAU email
```bash
git config --global user.name "Your Full Name"
git config --global user.email "your_email@my.erau.edu"
```

### Step 2: Generate an SSH Key
Run the command below and press `Enter` through all prompts to accept the default file location and no passphrase:
```bash
ssh-keygen -t ed25519 -C "your_email@my.erau.edu"
```

### Step 3: Add the SSH Key to Your GitHub Account
Print your public key in the terminal:
```bash
cat ~/.ssh/id_ed25519.pub
```
1. Highlight and copy the entire output line (it starts with `ssh-ed25519` and ends with your email).
2. On GitHub, click your **Profile Picture (top right) → Settings → SSH and GPG keys → New SSH key**.
3. Give it a clear title (e.g., `Personal Laptop` or `Lab Workstation`), paste the key into the **Key** box, and click **Add SSH key**.

---

## 2. How to Download (Clone) a Project Repository

Once your SSH key is added, navigate to the folder on your computer where you want to store your research files and run:

```bash
git clone git@github.com:erau-tpms-research-group/<repository-name>.git
cd <repository-name>
```
*(For example, to download our workflow template, replace `<repository-name>` with `tpmsWorkFlowTemplate`.)*

---

## 3. Daily Git Workflow (How to Pull & Push Your Work)

Every time you sit down to work on a project, follow these three steps in your terminal inside the repository folder:

### Step 1: Pull everyone else's latest changes FIRST (Before editing anything)
```bash
git pull
```

### Step 2: Check what files you modified
After editing code or OpenFOAM dictionaries, see which files changed:
```bash
git status
```
*(Red files are modified/untracked; green files are staged and ready to commit.)*

### Step 3: Save and upload (Push) your work to GitHub
Run these three commands in order to share your updates with the group:
```bash
# 1. Stage all modified files
git add .

# 2. Save a snapshot with a short message describing what you did
git commit -m "Briefly describe your update here"

# 3. Upload your changes to GitHub
git push
```

---

## 4. Group Rules & Best Practices

1. **Always run `git pull` before starting work** so you are never editing an outdated version of a file.
2. **Never run `git push --force`**—this can overwrite and erase your teammates' commits.
3. **Keep heavy simulation data out of GitHub:** Do not upload binary `.stl` files, generated meshes (`constant/polyMesh/`), decomposed processor folders (`processor*/`), or OpenFOAM time-step directories (`100/`, `200/`, etc.). Store raw simulation outputs on the lab's shared drive or workstation storage.
