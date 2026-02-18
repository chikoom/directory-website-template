# AI Agent Execution Guide - Directory Website Template

**Purpose:** This guide enables AI agents to execute the 28-stage directory website template system autonomously with minimal human intervention.

**Updated:** February 18, 2026

---

## 🎯 Overview for AI Agents

### Your Role
You are an autonomous agent responsible for executing a specific stage of the directory website template. You will:
1. Read the stage specifications from DIRECTORY_TEMPLATE_PROJECT.md
2. Gather inputs from previous stages or user guidance
3. Execute the stage tasks using specified tools
4. Validate outputs against acceptance criteria
5. Document completion and hand off to the next stage

### Critical Principles
- **Fail fast:** If validation fails, immediately flag and stop (don't force progress)
- **Explicit outputs:** Always produce documented, verifiable outputs
- **Tool specification:** Use ONLY the tools listed for each stage
- **Quality gates:** Respect human checkpoints (Stages 16, 24) - never override

---

## 📋 Stage Execution Templates

### PHASE 1: DISCOVERY & NICHE VALIDATION

---

#### **STAGE 1: Niche Ideation & Selection**

**Agent Role:** Market Researcher / Niche Analyst

**Input Requirements:**
- High-level interest areas or verticals to explore (from user)
- Access to research tools (internet search, Reddit, TikTok, Instagram)
- Template criteria from IMPLEMENTATION_SUMMARY.md

**Exact Tasks:**
1. Identify 5-10 potential directory niches from user input
2. For each niche, research using:
   - Reddit communities (search r/[niche], r/[industry])
   - TikTok hashtags related to the niche
   - Instagram communities and creator discussions
   - Industry forums and discussion boards
   - Google search trends and keyword volume
3. Evaluate each niche against success criteria:
   - ✅ Competitive (signals demand exists)
   - ✅ High transaction value ($100+)
   - ✅ Boring but important (less crowded)
   - ✅ Clear SEO search demand
4. Create niche evaluation spreadsheet with:
   - Niche name
   - Search volume estimate
   - Competition level
   - Transaction value estimate
   - Data availability assessment
   - Why this niche wins/fails
5. Recommend top 3 niches to the user for Stage 2

**Tools Needed:**
- Web search (Google, Bing)
- Reddit search
- TikTok/Instagram search
- Google Trends
- SEMrush or Ahrefs (if available)

**Expected Output:**
- `research/ideation-summary.md` containing:
  - 5-10 niches evaluated
  - Detailed scores for each criterion
  - Top 3 recommendations with rationale
  - Search volume data and links to sources

**Completion Verification:**
- [ ] At least 5 niches evaluated
- [ ] Each niche has research sources cited
- [ ] Top 3 ranked with clear criteria
- [ ] Output saved to research/ideation-summary.md
- [ ] Ready for Stage 2

---

#### **STAGE 2: Market Demand Validation**

**Agent Role:** Market Analyst / SEO Researcher

**Input Requirements:**
- Top 3 niches from Stage 1
- research/ideation-summary.md
- Access to SEO tools and research data

**Exact Tasks:**
1. For the top niche (selected for deep dive):
   - Research "how people find this [niche]"
   - Document common search queries (Google Search Console trends, SEMrush)
   - Identify pain points from customer research (Reddit threads, reviews)
   - Map decision drivers: What do customers actually need to decide?
   - Verify market size (addressable market estimation)
2. Interview research (lightweight):
   - Find 3-5 Reddit threads discussing the niche
   - Screenshot conversations showing problems and pain points
   - Note how people currently solve their problem
   - Identify information gaps
3. Competitive landscape:
   - Document existing solutions (directories, marketplaces, search methods)
   - Identify gaps in current solutions
   - Assess whether there's room for a better directory
4. Create market validation report

**Tools Needed:**
- Google Search Console
- SEMrush or Ahrefs
- Reddit search
- YouTube comments on niche-related videos
- Customer interview tools (Typeform, basic surveys)

**Expected Output:**
- `research/market-validation.md` containing:
  - Search demand data (monthly searches, trends)
  - Customer pain points (with Reddit/forum links)
  - Decision drivers (what do customers compare?)
  - Market size estimate
  - Competitive landscape analysis
  - Validation score: Ready for Stage 2.5? (YES/NO)

**Completion Verification:**
- [ ] Search volume documented with sources
- [ ] At least 3 pain points identified from user research
- [ ] Decision drivers clearly mapped
- [ ] Market size estimated
- [ ] Competitive analysis complete
- [ ] Validation score assigned
- [ ] Ready for Stage 2.5 (Critical Gate)

---

#### **STAGE 2.5: Data Scraping Proof-of-Concept** ⚠️ **CRITICAL GATE**

**Agent Role:** Data Engineer / Scraping Specialist

**Input Requirements:**
- Validated niche from Stage 2
- research/market-validation.md
- Access to OutScraper, Crawl4AI, and web scraping tools

**Exact Tasks:**
1. **Identify data sources:**
   - Google Maps businesses in niche (primary source)
   - Industry-specific directories (if exist)
   - Business listing websites
   - Company websites
   - Review sites
2. **Sample scrape (small test):**
   - Use OutScraper to scrape 50-100 entries from Google Maps
   - Document scraping method, fields captured, time taken
   - Assess data quality (completeness, accuracy)
3. **Verify scrapability:**
   - Check if websites are scrapable (robots.txt, terms of service)
   - Test Crawl4AI on 10 business websites in niche
   - Document success rate
   - Identify blocking or anti-scraping measures
4. **Quality assessment:**
   - Evaluate sample data quality (70%+ data present?)
   - Check for duplicates, bad entries, spam
   - Verify critical fields are available (phone, address, name, etc.)
   - Assess enrichment potential
5. **Create proof-of-concept report**

**Tools Needed:**
- OutScraper (Google Maps scraping)
- Crawl4AI (web scraping and verification)
- Python or Excel for data analysis
- Manual verification for 10-20 entries

**Expected Output:**
- `research/verification-report.md` containing:
  - Data source analysis
  - OutScraper test results (sample of 50-100 entries)
  - Crawl4AI test results on 10 websites
  - Data quality assessment
  - Pass/Fail decision with rationale

**GATE DECISION CRITERIA:**
- ✅ **PASS** if: 70%+ of entries are scrapeable AND 95%+ data quality OR clear data enrichment path exists
- ❌ **FAIL** if: <70% scrapeable OR <95% quality AND no enrichment path

**Completion Verification (PASS):**
- [ ] Sample data of 50+ entries collected
- [ ] Success rate documented (% scrapeable)
- [ ] Data quality checked (95%+ complete)
- [ ] 10 websites tested with Crawl4AI
- [ ] No hard blocking measures detected
- [ ] Pass/Fail decision justified with data
- [ ] Decision: **PASS** → Proceed to Stage 3
- [ ] Ready for next phase

**Completion Verification (FAIL):**
- [ ] Data quality below 70% scrapeable
- [ ] No clear enrichment path exists
- [ ] Decision: **FAIL** → Return to Stage 1
- [ ] Document why this niche failed
- [ ] Recommend exploring next niche from Stage 1

**Critical:** If FAIL, do NOT proceed. Return to Stage 1 and restart with next niche.

---

#### **STAGE 3: Business Model Decision**

**Agent Role:** Business Strategist / Product Manager

**Input Requirements:**
- Passed proof-of-concept from Stage 2.5
- research/market-validation.md
- research/verification-report.md

**Exact Tasks:**
1. **Analyze niche monetization potential:**
   - What's the transaction value per customer? (price of service they're buying)
   - Who are the target customers? (consumers vs businesses)
   - How do businesses currently make money in this niche?
2. **Evaluate three revenue models:**
   - Model A: Free Directory + Lead Generation (B2C users → B2B leads)
   - Model B: Free Directory + B2B SaaS (software for businesses in niche)
   - Model C: Marketplace/Booking Platform (take transaction commission)
3. **Select optimal model:**
   - Consider: operational complexity, revenue potential, competitive advantage
   - Compare to similar successful directories (Parting.com, APlaceForMom, GasBuddy)
   - Document reasoning
4. **Define initial SaaS features (if Model B):**
   - What operational problem do businesses face?
   - What software features would solve this?
   - Estimated price point ($99-500/month)?
5. **Create business model specification**

**Tools Needed:**
- Spreadsheet/document analysis
- Market research (similar directories)
- Cost/revenue modeling

**Expected Output:**
- `research/business-model.md` containing:
  - Niche opportunity summary
  - Three revenue models analyzed (pros/cons)
  - Selected business model with rationale
  - Revenue projections (conservative estimate)
  - If SaaS: feature specification and price point
  - Competitive positioning

**Completion Verification:**
- [ ] Three models analyzed
- [ ] Model selection justified
- [ ] Revenue model documented
- [ ] If SaaS: features and price defined
- [ ] Positioned against competitors
- [ ] Output ready for Phase 2 (Research & Planning)

---

## 🔧 PHASE 2: RESEARCH & PLANNING

_(Stages 4-8 continue with similar structure)_

### Quick Reference for Phase 2:
- **Stage 4:** Finalize data collection strategy (identify all data sources and scraping approach)
- **Stage 5:** Database schema design (define fields, structure, relationships)
- **Stage 6:** SEO & keyword strategy (target keywords, content strategy)
- **Stage 7:** SaaS feature specification (detailed features, mockups if applicable)
- **Stage 8:** Resource preparation (budgets, tools, external services needed)

---

## 📊 PHASE 3 & 4: DATA ACQUISITION & ENRICHMENT

### Quick Reference:
- **Stage 9:** Initial data scraping (execute large-scale scrape)
- **Stage 10-11:** Data cleaning & verification (quality control)
- **Stage 12:** Image collection (scrape images with rights management)
- **Stage 13-15:** Data enrichment (add attributes, reviews, context)
- **Stage 16:** Final data validation (**HUMAN CHECKPOINT** - requires manual review)

---

## 💻 PHASE 5: BUILD & DEVELOPMENT

### Quick Reference:
- **Stage 17:** Database implementation (load data into production DB)
- **Stage 18-19:** Website development (backend and frontend)
- **Stage 20:** SEO implementation (structured data, meta tags, site structure)
- **Stage 21:** SaaS development (if applicable)

---

## 🚀 PHASE 6: LAUNCH & MARKETING

### Quick Reference:
- **Stage 22:** Testing & QA (comprehensive testing)
- **Stage 23:** Pre-launch preparation (final checklists)
- **Stage 24:** Soft launch (**HUMAN CHECKPOINT** - limits audience)
- **Stage 25:** Public launch (full release)
- **Stage 26:** Organic SEO optimization (growth focus)
- **Stage 27:** SaaS customer acquisition (if applicable)
- **Stage 28:** Revenue tracking & optimization

---

## 🎬 INITIATING A NEW NICHE PROJECT

### Template Prompt for User / AI Agent to Start:

**When starting a new niche project, use this prompt:**

```
PROJECT INITIALIZATION PROMPT

Niche: [NICHE_NAME]
Vertical: [INDUSTRY_CATEGORY]
Target Users: [WHO_WILL_USE_THIS]
User Pain Point: [WHAT_PROBLEM_DOES_THIS_SOLVE]
Monetization Approach: [BUSINESS_MODEL_CHOICE]

EXECUTION REQUEST:
1. Clone the directory-website-template GitHub repository
2. Create a new Linear project: "[NICHE_NAME] Directory"
3. Link to "Directory Website System" initiative
4. Begin execution at Stage 1 (Niche Ideation & Selection)
5. For each stage, follow the AI Agent Execution Guide
6. Validate outputs against acceptance criteria
7. Report progress to [USER_EMAIL]

TIMELINE:
- Estimated Phase 1 completion: [X] days
- Estimated full project timeline: [X] weeks

BEGIN EXECUTION
```

### Steps to Execute:
1. Read this AI Agent Execution Guide
2. Read DIRECTORY_TEMPLATE_PROJECT.md for full stage details
3. Read IMPLEMENTATION_SUMMARY.md for project overview
4. Clone GitHub repo: https://github.com/chikoom/directory-website-template
5. Create Linear project with 28 issues
6. Start at Stage 1 with the templates provided
7. Follow the exact specifications for each stage

---

## ✅ Validation Checklist for AI Agents

**Use this checklist for every stage completion:**

- [ ] Input requirements met (all necessary data available)
- [ ] All tasks completed as specified
- [ ] Tools used are those listed for the stage
- [ ] Output produced in exact format specified
- [ ] Output saved to correct directory
- [ ] Acceptance criteria all verified
- [ ] Documentation complete with sources/links
- [ ] Ready to hand off to next stage
- [ ] No blocking issues identified

**If ANY checkbox is unchecked:** Do not proceed to next stage. Flag the issue to the user.

---

## 🚨 Critical Gates & Human Checkpoints

**Stage 2.5 (Critical Gate):**
- If data is not 70%+ scrapeable: **STOP and return to Stage 1**
- Never force a niche past this gate if data isn't available

**Stage 16 (Human Checkpoint):**
- **PAUSE** at this stage for user review and approval
- User must validate data quality before development begins
- Do not proceed to Stage 17 until approved

**Stage 24 (Human Checkpoint):**
- **PAUSE** at this stage for limited audience testing
- User can provide feedback before public launch
- Gather metrics and feedback before Stage 25

---

## 📚 Key Files Reference

For AI agents executing this template:

1. **DIRECTORY_TEMPLATE_PROJECT.md** - Read this for detailed stage specifications
2. **IMPLEMENTATION_SUMMARY.md** - Read this for project structure overview
3. **VIDEO_NOTES.md** - Read this for business model context and insights
4. **This file (AI_AGENT_EXECUTION_GUIDE.md)** - Use for execution guidance and templates

---

## 🔗 Tools & Resources

**Essential Tools:**
- **OutScraper** - Google Maps data scraping
- **Crawl4AI** - Web scraping and verification
- **Claude API/Vision** - Data analysis and image quality assessment
- **Linear API** - Project management automation
- **GitHub** - Version control and documentation

**Optional Tools:**
- SEMrush/Ahrefs - SEO research
- Typeform - Customer surveys
- Python/Node.js - Data processing scripts
- AWS/Vercel/Supabase - Hosting (for Stage 17+)

---

**Last Updated:** February 18, 2026
**Status:** Ready for AI agent execution
**Version:** 1.0
