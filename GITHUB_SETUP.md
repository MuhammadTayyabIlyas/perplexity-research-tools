# 🚀 GitHub Setup Guide

## Quick Steps to Push to GitHub

### 1️⃣ Create a New Repository on GitHub

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `perplexity-ai-research-tools` (or your choice)
3. Description: "AI-powered academic research and fact-checking tools using Perplexity Sonar API"
4. **DO NOT** initialize with README (we already have one)
5. Keep it **Public** or **Private** as you prefer
6. Click "Create repository"

### 2️⃣ Connect Your Local Repository

```bash
# Replace YOUR_USERNAME with your GitHub username
git remote add origin https://github.com/YOUR_USERNAME/perplexity-ai-research-tools.git
```

### 3️⃣ Push to GitHub

```bash
# Push your code to GitHub
git push -u origin main
```

If prompted for credentials:
- **Username:** Your GitHub username
- **Password:** Use a Personal Access Token (not your password)

### 4️⃣ Get Personal Access Token (if needed)

1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Give it a name: "Perplexity Research Tools"
4. Select scopes: `repo` (full control)
5. Click "Generate token"
6. **Copy the token immediately** (you won't see it again!)
7. Use this token as your password when pushing

### 5️⃣ Update README with Your LinkedIn

Open `README.md` and replace these placeholders:

```markdown
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](YOUR_LINKEDIN_URL_HERE)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=for-the-badge&logo=gmail)](mailto:YOUR_EMAIL_HERE)
```

With your actual:
- LinkedIn URL (e.g., `https://www.linkedin.com/in/muhammad-tayyab-ilyas`)
- Email address (e.g., `tayyab@example.com`)

Then commit and push the update:

```bash
git add README.md
git commit -m "Update contact information in README"
git push
```

## ✅ Verification Checklist

- [ ] API key (`.pplx_api_key`) is NOT in repository
- [ ] `.gitignore` is working correctly
- [ ] README displays properly on GitHub
- [ ] All badges are visible
- [ ] LinkedIn and email links are updated
- [ ] Project description is clear

## 🎨 Make Your Repository Stand Out

### Add Topics (Tags)
On your GitHub repository page:
1. Click "Add topics"
2. Add: `ai`, `perplexity`, `research-tools`, `fact-checking`, `python`, `cli`, `academic-research`, `nlp`

### Add Repository Description
Set the description to:
```
🤖 AI-powered academic research finder and fact-checker using Perplexity Sonar API | Python CLI tools
```

### Enable GitHub Pages (Optional)
1. Go to Settings → Pages
2. Source: Deploy from branch
3. Branch: main, folder: / (root)
4. Your README will be visible as a webpage!

## 🔧 Useful Git Commands

```bash
# Check repository status
git status

# View commit history
git log --oneline --graph

# See what files are ignored
git status --ignored

# Add more files
git add <filename>
git commit -m "Your message"
git push

# Create a new branch
git checkout -b feature/new-feature

# Switch back to main
git checkout main
```

## 🚨 Important Security Notes

**Never commit these files:**
- ✅ `.pplx_api_key` - Your actual API key
- ✅ `venv/` - Virtual environment
- ✅ `.claude/` - Claude Code configuration
- ✅ `__pycache__/` - Python cache

These are already in `.gitignore`, but double-check before pushing!

## 📞 Need Help?

If you encounter issues:
1. Check that git is installed: `git --version`
2. Verify remote is set: `git remote -v`
3. Check your GitHub token permissions
4. Ensure you have internet connection

---

**Ready to share your amazing project with the world! 🌟**
