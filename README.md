# 🤖 Perplexity AI Research Tools

<div align="center">

![AI Research](https://img.shields.io/badge/AI-Research%20Tools-blue?style=for-the-badge&logo=openai)
![Python](https://img.shields.io/badge/Python-3.8+-green?style=for-the-badge&logo=python)
![Perplexity](https://img.shields.io/badge/Perplexity-API-purple?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**A powerful collection of command-line tools powered by Perplexity's Sonar API for academic research and fact-checking**

[Features](#-features) • [Installation](#️-installation) • [Usage](#-usage) • [Examples](#-quick-examples) • [Author](#-author)

---

</div>

## 🌟 Features

<table>
<tr>
<td width="50%">

### 📚 Academic Research Finder
✨ Search academic literature and research papers
📊 Get comprehensive summaries with citations
🎓 Access scholarly sources from journals & databases
📄 Multiple output formats (readable & JSON)
🚀 Fast and efficient API-powered searches

</td>
<td width="50%">

### ✅ Fact Checker CLI
🔍 Verify claims for factual accuracy
❌ Identify false or misleading information
📖 Get detailed explanations with evidence
🌐 Check articles from text, files, or URLs
⚡ Real-time fact verification

</td>
</tr>
</table>

---

## 📋 Prerequisites

| Requirement | Description |
|------------|-------------|
| 🐍 **Python** | Version 3.8 or higher |
| 🔑 **API Key** | Perplexity API key ([Get it here](https://www.perplexity.ai/settings/api)) |
| 💻 **System** | Ubuntu/Linux or WSL on Windows |

---

## 🛠️ Installation

### **Step 1:** Clone the Repository

```bash
git clone <your-repository-url>
cd research
```

### **Step 2:** Create Virtual Environment

```bash
python3 -m venv venv
```

### **Step 3:** Install Dependencies

<details>
<summary>📦 Click to expand installation options</summary>

#### For Academic Research Finder:
```bash
./venv/bin/pip install -r requirements.txt
```

#### For Fact Checker CLI:
```bash
./venv/bin/pip install -r fact_checker_requirements.txt
```

#### Or install both at once:
```bash
./venv/bin/pip install -r requirements.txt -r fact_checker_requirements.txt
```

</details>

### **Step 4:** Set Up API Key

```bash
# Copy example file
cp .pplx_api_key.example .pplx_api_key

# Add your actual API key
echo "your-actual-api-key-here" > .pplx_api_key

# Secure the file
chmod 600 .pplx_api_key
```

**💡 Alternative:** Set as environment variable:
```bash
export PPLX_API_KEY=your-api-key-here
```

### **Step 5:** Make Scripts Executable

```bash
chmod +x research_finder.py fact_checker.py per check
```

### **Step 6:** (Optional) Add to PATH

```bash
echo 'export PATH="/path/to/research:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

---

## 📖 Usage

### 🔬 Academic Research Finder

<table>
<tr>
<th>Command</th>
<th>Description</th>
</tr>
<tr>
<td>

```bash
./per "quantum computing"
```

</td>
<td>Basic research query</td>
</tr>
<tr>
<td>

```bash
./per "AI in healthcare" --json
```

</td>
<td>Get JSON output</td>
</tr>
<tr>
<td>

```bash
./per "machine learning" -m sonar
```

</td>
<td>Use specific model</td>
</tr>
</table>

**📝 Available Arguments:**

| Argument | Description | Default |
|----------|-------------|---------|
| `query` | Your research question | *Required* |
| `-m, --model` | Perplexity model to use | `sonar-pro` |
| `-k, --api-key` | API key (if not in file) | From `.pplx_api_key` |
| `-p, --prompt-file` | Custom system prompt | `system_prompt.md` |
| `-j, --json` | Output as JSON | `false` |

### 🔎 Fact Checker CLI

<table>
<tr>
<th>Command</th>
<th>Description</th>
</tr>
<tr>
<td>

```bash
./check "Earth is flat"
```

</td>
<td>Check a claim</td>
</tr>
<tr>
<td>

```bash
./venv/bin/python3 fact_checker.py -f article.txt
```

</td>
<td>Check file content</td>
</tr>
<tr>
<td>

```bash
./venv/bin/python3 fact_checker.py -u https://example.com
```

</td>
<td>Check URL article</td>
</tr>
</table>

**📝 Available Arguments:**

| Argument | Description |
|----------|-------------|
| `-t, --text` | Text to fact check |
| `-f, --file` | File path to check |
| `-u, --url` | URL to check |
| `-m, --model` | Model to use (default: `sonar-pro`) |
| `-j, --json` | Output as JSON |
| `--structured-output` | Enable structured output (Tier 3+ only) |

---

## 🎯 Quick Examples

### 📚 Research Example

```bash
./per "What is the impact of AI on healthcare?"
```

**Output:**
```
✅ Research Complete!

📝 SUMMARY:
AI is transforming healthcare through improved diagnostics, personalized
treatment plans, drug discovery acceleration, and administrative efficiency...

🔗 SOURCES:
  1. https://www.nature.com/articles/...
  2. https://www.ncbi.nlm.nih.gov/...
  ...
```

### ✅ Fact Check Example

```bash
./check "Vaccines cause autism"
```

**Output:**
```
🔍 Fact checking in progress...

🔴 OVERALL RATING: FALSE

📝 SUMMARY:
This claim has been thoroughly debunked by extensive scientific research...
```

---

## ⚙️ Configuration

### 🎨 Custom System Prompts

Create custom prompts to tailor AI behavior:

1. Create `system_prompt.md` in project directory
2. Write your custom prompt
3. Tools will automatically use it

Or specify custom prompt:
```bash
./per "your query" --prompt-file /path/to/custom_prompt.md
```

---

## 📊 Output Formats

<table>
<tr>
<th>Format</th>
<th>Description</th>
<th>Use Case</th>
</tr>
<tr>
<td>🎨 <b>Human-readable</b></td>
<td>Clear, formatted output with sections</td>
<td>Direct reading and analysis</td>
</tr>
<tr>
<td>📋 <b>JSON</b></td>
<td>Structured data format</td>
<td>Programmatic use, integration</td>
</tr>
</table>

---

## 🔒 Security Notes

> ⚠️ **Important Security Practices:**

- ✅ Never commit `.pplx_api_key` to version control
- ✅ Set file permissions: `chmod 600 .pplx_api_key`
- ✅ Use `.gitignore` to exclude sensitive files
- ✅ Rotate API keys periodically
- ✅ Use environment variables in production

---

## ⚠️ Known Limitations

<details>
<summary>Click to view limitations</summary>

### Fact Checker CLI:
- Structured outputs require Tier 3+ API access
- May encounter 400 errors on lower API tiers
- **Workaround:** Use Research Finder for claim verification

### General:
- Accuracy depends on Perplexity API's data sources
- Not a replacement for professional fact-checking
- Complex queries may need refinement

</details>

---

## 🐛 Troubleshooting

<details>
<summary>❓ API Errors (400 Bad Request)</summary>

- Verify API key is valid and properly configured
- Check your API tier (Fact Checker needs Tier 3+ for structured outputs)
- Use Research Finder as alternative for verification

</details>

<details>
<summary>❓ Import Errors</summary>

```bash
# Install all dependencies
./venv/bin/pip install -r requirements.txt -r fact_checker_requirements.txt

# Fix lxml.html.clean error
./venv/bin/pip install lxml_html_clean
```

</details>

<details>
<summary>❓ Command Not Found</summary>

```bash
# Make scripts executable
chmod +x research_finder.py fact_checker.py per check

# Update PATH
echo 'export PATH="$(pwd):$PATH"' >> ~/.bashrc
source ~/.bashrc
```

</details>

---

## 📚 Additional Resources

| Resource | Link |
|----------|------|
| 📖 **Perplexity API Docs** | [docs.perplexity.ai](https://docs.perplexity.ai/) |
| 🔑 **Get API Key** | [perplexity.ai/settings/api](https://www.perplexity.ai/settings/api) |
| 📚 **API Cookbook** | [docs.perplexity.ai/cookbook](https://docs.perplexity.ai/cookbook) |

---

## 📁 Project Structure

```
research/
├── 📄 README.md                        # Documentation
├── 🐍 research_finder.py               # Academic Research Finder
├── 🐍 fact_checker.py                  # Fact Checker CLI
├── 📦 requirements.txt                 # Research Finder dependencies
├── 📦 fact_checker_requirements.txt    # Fact Checker dependencies
├── 🔧 per                             # Research wrapper script
├── 🔧 check                           # Fact check wrapper script
├── 📝 .pplx_api_key.example           # Example API key file
├── 🔐 .pplx_api_key                   # Your API key (gitignored)
├── 🚫 .gitignore                      # Git ignore rules
└── 📁 venv/                           # Virtual environment (gitignored)
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

Feel free to check the [issues page](#) if you want to contribute.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

**Note:** This project uses Perplexity's Sonar API. Please refer to [Perplexity's Terms of Service](https://www.perplexity.ai/hub/terms) for API usage guidelines.

---

## 👨‍💻 Author

<div align="center">

### **Muhammad Tayyab ILYAS**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](YOUR_LINKEDIN_URL_HERE)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/tayyabcheema777)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=for-the-badge&logo=gmail)](mailto:YOUR_EMAIL_HERE)

**Passionate about AI, Research, and Building Innovative Tools**

</div>

---

## 🙏 Acknowledgments

- 🔮 Built using [Perplexity's Sonar API](https://www.perplexity.ai/)
- 📚 Inspired by [Perplexity API Cookbook](https://docs.perplexity.ai/cookbook)
- 🌟 Special thanks to the open-source community

---

<div align="center">

### ⭐ Star this repository if you find it helpful!

**Made with ❤️ by Muhammad Tayyab ILYAS**

</div>
