# Linux & Git Basics Cheatsheet

A quick reference guide for basic terminal operations, file manipulation, text search, file permissions, and essential Git workflows.

## 1. Directory & Navigation Commands

| Command | Description | Example |
| ----- | ----- | ----- |
| `pwd` | **Print Working Directory** - Displays the absolute path of your current location. | `pwd` |
| `mkdir` | **Make Directory** - Creates a new folder. | `mkdir project1` |
| `cd` | **Change Directory** - Moves into a specified folder. | `cd project1` |
| `ls -l` | **List Long Format** - Prints directory contents alongside details like file permissions, size, and owner. | `ls -l` |

## 2. File Creation & Management

| Action | Command |
| ----- | ----- |
| **Create empty files** | `touch file1.txt file2.txt` |
| **Write text via stdout redirection** | `echo 'Your text' > file1.txt` |
| **Edit text using interactive editor** | `nano file2.txt` |
| **Copy file into a folder** | `cp file1.txt project1/` |
| **Move file into a folder** | `mv file2.txt project1/` |

## 3. Reading & Concatenating Files

* **View file content in terminal:**

  ```bash
  cat file1.txt
  ```

* **Combine multiple files into a single new file:**

  ```bash
  cat file1.txt file2.txt > file3.txt
  ```

## 4. Searching Text with `grep`

* **Search across multiple files and list matching filenames (`-l`):**

  ```bash
  grep -l 'keyword' file1.txt file2.txt
  ```

* **Search a single file and display line numbers (`-n`):**

  ```bash
  grep -n 'keyword' file1.txt
  ```

## 5. File Permissions (`chmod`)

Permissions in Linux are divided into three groups: **Owner (User)**, **Group**, and **Others**.

### Permission Values Reference

| Number | Permission | Symbol |
| ----- | ----- | ----- |
| `4` | Read | `r` |
| `2` | Write | `w` |
| `1` | Execute | `x` |
| `0` | No Access | `-` |

*(Combine numbers to stack permissions: `4 + 2 = 6` for Read & Write, `4 + 2 + 1 = 7` for Full Access).*

### Practical Examples

* **Read-only for owner, no access for group/others (`400`):**

  ```bash
  chmod 400 file1.txt
  ```

* **Full permissions for owner, read/execute for group & others (`755`):**
  *(Common for executable scripts and directories)*

  ```bash
  chmod 755 project_folder
  ```

* **Read and write for owner, read-only for group & others (`644`):**
  *(Standard default permission for regular text files)*

  ```bash
  chmod 644 file2.txt
  ```

* **Full access for everyone (`777`):**
  *(Use with caution! Gives read, write, and execute permissions to all users)*

  ```bash
  chmod 777 shared_folder
  ```

## 6. Git Setup & Workflow

### First-Time Git Configuration

Set your identity before making commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Explanation of Core Git Commands

| Command | What It Does & How It Works |
| ----- | ----- |
| `git clone <url>` | **Downloads a repository.** Downloads a complete copy of a remote Git repository onto your local computer, sets up the default `origin` connection, and creates a local directory for it. |
| `git pull` | **Fetches and merges remote changes.** Downloads the latest commits from the remote repository (e.g., GitHub) and merges them directly into your current local branch so your code stays up to date. |
| `git status` | **Checks the repository state.** Compares local files to the last commit to show untracked files (new), modified files, and staged changes ready to be committed. |
| `git add .` | **Stages changes.** Moves modified or new files into the *Staging Area* (draft area) preparing them to be included in the next commit snapshot. |
| `git commit -m "msg"` | **Saves a snapshot locally.** Permanently saves the staged changes as a checkpoint in your local Git repository's history attached with a timestamp and your message. |
| `git push` | **Uploads commits.** Sends all your local commits over the internet to update the remote repository (e.g., GitHub). |

### Git Workflow Visualized

```text
[ Remote Repository ] (GitHub / Server)
        │
        │  git pull  (Fetch & Merge latest changes down)
        ▼
[ Working Directory ] 
        │
        │  1. git add .
        ▼
[   Staging Area   ]   (Preparing changes)
        │
        │  2. git commit -m "message"
        ▼
[ Local Repository ]   (Saved on your computer)
        │
        │  3. git push  (Upload local commits up)
        ▼
[ Remote Repository ] (GitHub / Server)
```

### Step-by-Step Repository Setup

1. **Clone a Remote Repository:**

   ```bash
   git clone <copied_repo_url>
   ```

2. **Navigate into the Repository & Check Status:**

   ```bash
   cd <repo-name>
   git status
   ```

3. **Fetch Latest Changes (Good Habit Before Editing):**

   ```bash
   git pull
   ```

4. **Update or Add `README.md`:**

   * Create/Open `README.md` in a text editor (e.g., VS Code, Notepad++, Sublime).
   * Add your **name** in the first row.
   * Add your **program details** in the introduction section.

5. **Stage, Commit, and Push Changes:**

   ```bash
   git add .
   git commit -m "Add author details and intro to README"
   git push
   ```

### Adding Exercises / Notebooks Workflow

1. **Keep Local Syncing Up to Date:**

   ```bash
   git pull
   ```

2. **Organize Your Files:**

   * Gather all your prework Jupyter notebook files.
   * Move them into your local repository folder.
   * Ensure each notebook has a clear, descriptive name based on its topic (e.g., `01_python_basics.ipynb`, `02_dictionary_operations.ipynb`).

3. **Sync Changes to Remote Repository:**

   ```bash
   git add .
   git commit -m "Add prework practice notebooks"
   git push
   ```