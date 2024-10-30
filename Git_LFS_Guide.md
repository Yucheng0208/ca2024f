
# Git Large File Storage (LFS) 使用說明 / Git Large File Storage (LFS) User Guide

## 目錄 / Table of Contents
1. [簡介 / Introduction](#簡介--introduction)
2. [安裝 Git LFS / Installing Git LFS](#安裝-git-lfs--installing-git-lfs)
3. [使用 Git LFS 跟蹤大文件 / Tracking Large Files with Git LFS](#使用-git-lfs-跟蹤大文件--tracking-large-files-with-git-lfs)
4. [提交跟蹤的文件 / Committing Tracked Files](#提交跟蹤的文件--committing-tracked-files)
5. [克隆與拉取包含 LFS 文件的倉庫 / Cloning and Pulling Repositories with LFS Files](#克隆與拉取包含-lfs-文件的倉庫--cloning-and-pulling-repositories-with-lfs-files)
6. [常用操作命令 / Common Commands](#常用操作命令--common-commands)
7. [注意事項 / Important Notes](#注意事項--important-notes)
8. [總結 / Summary](#總結--summary)

---

## 簡介 / Introduction

Git Large File Storage (LFS) 是一個 Git 擴展工具，用來解決 Git 在處理大型文件時的性能問題。
Git Large File Storage (LFS) is an extension tool for Git, designed to solve performance issues when handling large files in Git.

---

## 安裝 Git LFS / Installing Git LFS

1. **下載與安裝 Git LFS**  
   根據系統安裝 [Git LFS](https://git-lfs.github.com/)，或使用命令行安裝：
   
   According to your system, install [Git LFS](https://git-lfs.github.com/) or use command line installation:
   
   ```bash
   # macOS
   brew install git-lfs

   # Ubuntu/Debian
   sudo apt install git-lfs

   # Windows
   choco install git-lfs
   ```

2. **初始化 Git LFS / Initializing Git LFS**
   安裝完成後，執行以下命令來初始化 LFS：
   After installation, run the following command to initialize LFS:

   ```bash
   git lfs install
   ```

---

## 使用 Git LFS 跟蹤大文件 / Tracking Large Files with Git LFS

使用 `git lfs track` 命令將特定類型或大小的文件添加到 LFS 的跟蹤範圍中：
Use `git lfs track` command to add specific types or large files to the tracking scope of LFS:

```bash
# 跟蹤指定文件類型，例如所有的 .psd 文件
git lfs track "*.psd"
# Track specific file types, e.g., all .psd files
```

---

## 提交跟蹤的文件 / Committing Tracked Files

當您使用 Git LFS 跟蹤文件類型後，正常使用 Git 命令提交這些文件：
After tracking file types with Git LFS, commit these files using regular Git commands:

```bash
git add .gitattributes
git add <filename> # 或 git add .
git commit -m "Add large files with LFS tracking"
git push origin <branch>
```

---

## 克隆與拉取包含 LFS 文件的倉庫 / Cloning and Pulling Repositories with LFS Files

克隆或拉取包含 LFS 文件的倉庫時，LFS 會自動拉取文件：
LFS automatically pulls files when cloning or pulling repositories that include LFS files:

```bash
git clone <repository_url>
```

或使用 `git lfs pull` 來獲取所有 LFS 文件：
Alternatively, use `git lfs pull` to retrieve all LFS files:

```bash
git lfs pull
```

---

## 常用操作命令 / Common Commands

- **查看 LFS 跟蹤的文件 / View Tracked Files**:
  ```bash
  git lfs track
  ```

- **取消 LFS 跟蹤 / Untrack Files**:
  ```bash
  git lfs untrack "*.psd"
  git add .gitattributes
  git commit -m "Untrack .psd files from LFS"
  ```

- **查看 LFS 文件狀態 / View LFS File Status**:
  ```bash
  git lfs ls-files
  ```

---

## 注意事項 / Important Notes

1. **存儲限額 / Storage Limits**: 
   部分 Git 平台如 GitHub 對 LFS 的免費存儲空間有限制。
   Some Git platforms like GitHub have limitations on free storage for LFS.

2. **增量式存儲 / Incremental Storage**:
   LFS stores the latest version of each file, which may increase storage usage.

3. **遠端配置 / Remote Configuration**:
   If using Git LFS on a private server, ensure the server supports LFS.

---

## 總結 / Summary

Git LFS 能夠大幅度提升 Git 對大文件的處理能力，適合包含大文件的項目。通過安裝、初始化、文件跟蹤、提交和遠程管理，Git LFS 可以讓您的大文件管理變得更加簡便高效。
Git LFS significantly enhances Git's capability to handle large files, making it ideal for projects with large data files. Installation, initialization, file tracking, committing, and remote management make Git LFS efficient for managing large files.

