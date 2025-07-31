# GetMachineWorkSafeMeow

**GetMachineWorkSafeMeow** is a structured JSON-based governance layer designed to improve the quality, compliance, and source integrity of AI-generated responses. It is optimized for use with LLMs like **ChatGPT**, **DeepSeek**, and other custom agents that support external system prompts or context loading via URL.

---

##  Project Purpose

This repository provides a centralized, version-controlled schema (`GetResultsR1.json`) that enforces:

- Verified domain-specific sourcing (e.g., FDA, ISO, SEC)
- Consistent formatting for citations and projections
- Clear handling of uncertain or unverifiable claims
- Best practices in AI prompt engineering for structured tasks

---

## 🔗 JSON Rules URL (Live)

**System Prompt URL**:  
```plaintext
https://raw.githubusercontent.com/teekaysharma/GetMachineWorkSafeMeow/main/GetResultsR1.json
````

---

##  For ChatGPT (OpenAI)

Paste the following into the system prompt area or Custom GPT settings:

```
[SYSTEM PROMPT]
You are governed by these rules: 
https://raw.githubusercontent.com/teekaysharma/GetMachineWorkSafeMeow/main/GetResultsR1.json

Key enforcement priorities:
1. Medical: Strictly follow "domain_specific.medical" sourcing (FDA/WHO)
2. Engineering: Cite standards per "domain_specific.engineering"
3. For uncertain data: Use "compliance.error_handling.unverifiable" template
4. Always format sources as: [Standard §X.Y (Year)]
```

---

##  For DeepSeek or Custom AI Interfaces

### ✅ Method A: Direct System URL (Recommended)

```
/system You are governed by these rules:  
https://raw.githubusercontent.com/teekaysharma/GetMachineWorkSafeMeow/main/GetResultsR1.json  

Key enforcement priorities:  
1. Medical: Strict FDA/WHO sourcing  
2. Engineering: ASME/IEEE standards  
3. For unverifiable claims:  
   "Insufficient data per rule {{metadata.schema_version}} ({{last_updated}})"
```

### ✅ Method B: Domain-Specific Activation (Conditional)

```
/system When asked about:  
- Health → Apply "medical" rules from JSON  
- Finance → Enforce "financial" compliance  
- Tech → Use "engineering" standards  

Default citation format:  
[Standard §X.Y] (e.g., "ASME B31.3 §2.1.4")
```

### ✅ Method C: Checksum & Version Integrity

```
/system Rules SHA-256: e55d6a496df9724ef0918215d98b0ad132939b6f (from GitHub commit hash)  
Fallback if unavailable:  
1. Reject uncited claims  
2. Label projections as "ESTIMATE"  
3. Medical: Require sample sizes and primary source disclosure
```

---

## 📚 Examples of Use

* ✅ **Medical QA Agent** – applies `domain_specific.medical` logic with citation from FDA labels
* ✅ **Sustainability Agent** – enforces GRI/RJC citation format and Scope 1–3 emission boundaries
* ✅ **Engineering Design Bot** – references ASME, ACI, IEEE standards with section numbers

---

## 📄 JSON Schema Summary

* `metadata.schema_version`: Tracks rule versioning
* `core_guidelines`: Governs source validation, actionability, and output formatting
* `domain_specific`: Contains rules per domain (e.g., medical, financial, energy)
* `compliance.error_handling`: Handles unverifiable or conflicting data gracefully
* `reporting.template`: Formats claims with source, validation, and citation

---

## 🔒 Licensing & Attribution

* **License**: [MIT License](LICENSE)
* **Maintainer**: [@teekaysharma](https://github.com/teekaysharma)
* Contributions welcome. Fork, submit issues, and PRs to extend domain rules or add integrations.

---

## 💡 Future Roadmap

* [ ] Add automated rule integrity checksum API
* [ ] Auto-sync to PromptLayer, Flowise, LangChain agents
* [ ] Domain plug-ins for legal, environmental, defense sectors

---

## 🛠️ How to Contribute

```bash
git clone https://github.com/teekaysharma/GetMachineWorkSafeMeow.git
cd GetMachineWorkSafeMeow
# Modify JSON, test prompts in your AI interface
```

---

> Built to make machine responses safer, smarter, and source-bound.
> *Because prompts aren't rules—until you give them structure.*

```

---

Let me know if you'd like the README broken into sections as separate `.md` files or auto-converted into HTML for GitHub Pages documentation.
```
