# 🚀 ASCII Hook Demo

![Git](https://img.shields.io/badge/Git-Hooks-orange)
![Status](https://img.shields.io/badge/Project-Complete-brightgreen)

## 📌 Overview

This project demonstrates a Git pre-commit hook that prevents committing files with non-ASCII filenames.

## 🔐 Pre-Commit Hook

The hook checks staged files and blocks commits if filenames contain non-ASCII characters.

### ❌ Blocked Examples

- résumé.txt
- café.txt
- 文件.txt
- test🔥.txt

### ✅ Allowed Examples

- resume.txt
- login_1.txt
- report-2026.txt
- DATA.md

## ⚙️ How It Works

1. Git runs the pre-commit hook before commit
2. Hook scans staged filenames
3. Non-ASCII characters are detected
4. Commit is blocked if invalid filenames exist
5. Developer renames the files and commits again

## 🧪 Test Workflow

```bash
touch résumé.txt
git add résumé.txt
git commit -m "test non-ascii file"

ERROR: Non-ASCII filename detected.

ascii-hook-demo/
├── hooks/
│   └── pre-commit.txt
├── README.md
├── DATA.md
├── file.txt
├── login_1.txt
├── normal.txt
├── report-2026.txt
├── resume.txt
├── resume2.txt
└── test.txt




