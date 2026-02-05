# GenAI Usage Log

**Project**: Automated EDA System with LLM Integration  
**Author**: [Ishita Pawar, Atharva Bendre]  
**Date**: February 4, 2026

---

## Tools Used

1. **Claude (Anthropic)** - via claude.ai web interface
2. **ChatGPT (OpenAI)** - GPT-4
3. **GitHub Copilot** - code completion

---

## Session 1: Initial Code Structure

### Date: February 3, 2026
### Tool: Claude 3.5 Sonnet

**Prompt:**
```
I need to build an automated EDA system for a data mining assignment. The system should:
- Accept CSV files
- Compute descriptive statistics (mean, median, mode, IQR, outliers)
- Generate at least 5 visualizations
- Produce insights using an LLM

Can you help me structure the code with modular functions?
```

**Response Summary:**
Claude provided a modular structure with separate functions for:
- Dataset overview
- Column type detection
- Numeric/categorical summaries
- Visualization generation
- Main pipeline function

**What I Changed/Verified:**
- Verified the outlier detection formula (1.5×IQR rule) was correct
- Added mode calculation which was missing
- Changed plot colors to match assignment aesthetic (pink)
- Added missing value percentage calculations 
- Removed suggestion to use plotly (assignment requires matplotlib)

---

## Session 2: LLM Integration for Insights

### Date: February 3, 2026
### Tool: Claude 3.5 Sonnet

**Prompt:**
```
How can I integrate an LLM to generate insights from computed statistics? 
I want to ensure:
1. The LLM doesn't hallucinate numbers
2. All insights reference actual computed statistics
3. There's a fallback if API is unavailable

Show me the code pattern.
```

**Response Summary:**
Claude suggested:
1. Creating a structured dictionary of all computed stats
2. Passing this to LLM with strict prompt instructions
3. Implementing a rule-based fallback

**What I Changed/Verified:**
- Added explicit "DO NOT INVENT NUMBERS" instruction to prompt
- Verified the statistics dictionary includes all necessary fields
- Implemented mock insights function for offline use
- Added try-except for robust error handling
- Modified: Changed from GPT-4 to Claude API in example code

---

## Session 3: Visualization Improvements

### Date: February 4, 2026
### Tool: GitHub Copilot

**Usage:**
- Used autocomplete for matplotlib boilerplate code
- Suggested sns.heatmap parameters

**What I Changed/Verified:**
- Manually set figure sizes for consistency
- Added proper axis labels (Copilot initially forgot these)
- Set DPI to 150 for high-quality outputs
- Rejected suggestion to use interactive plots (assignment needs static)

---

## Session 4: Limitations Section

### Date: February 4, 2026
### Tool: ChatGPT-4

**Prompt:**
```
For a data analysis project, I need to write a "limitations and biases" section.
The dataset might have:
- Missing values
- Outliers  
- Small sample size
- Unknown sampling method

What should I include in the limitations discussion?
```

**Response Summary:**
ChatGPT provided comprehensive list:
- Missingness patterns (MCAR, MAR, MNAR)
- Sample size and power
- Outlier impact
- Sampling bias
- Temporal coverage
- Feature coverage

**What I Changed/Verified:**
- Adapted generic suggestions to my specific code
- Added automatic detection of which limitations apply
- Made recommendations actionable and specific
- Modified: Tied limitations to actual computed statistics


---

## Session 6: Code Review and Bug Fixes

### Date: February 4, 2026
### Tool: Claude 3.5 Sonnet

**Prompt:**
```
Review this code for bugs:
[pasted my visualization function]

I think the plots aren't displaying because of plt.close() placement.
```

**Response Summary:**
Claude identified the issue: `plt.close()` was called before `plt.show()`.

**What I Changed/Verified:**
- Fixed: Removed plt.close() from before plt.show()
- Verified: Tested plots now display correctly
- Added: plt.tight_layout() for better spacing

---

## Summary of GenAI Contribution

### What GenAI Did Well:
- Provided solid initial code structure
- Suggested best practices for LLM integration
- Generated comprehensive documentation templates
- Caught bugs in my code

### What I Had to Fix/Verify:
- Mathematical formulas (IQR, outlier detection)
- Plot aesthetics and labeling
- Assignment-specific requirements
- Error handling edge cases
- File paths and naming conventions


## Verification Process

For every piece of GenAI-generated code, I:

1.  **Tested** it with actual data
2.  **Verified** mathematical correctness
3.  **Checked** against assignment requirements  
4.  **Reviewed** for edge cases
5.  **Documented** what was changed

---

## Declaration

I certify that:
- All GenAI usage has been documented in this log
- I understand and can explain every line of code in my submission
- I verified the correctness of all statistics and outputs
- The insights generated are based on actual computed data, not hallucinations

**Signature**: [Ishita Pawar, Atharva Bendre]  
**Date**: February 4, 2026
