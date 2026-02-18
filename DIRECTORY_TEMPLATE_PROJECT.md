# [AIDW] Directory Website Template Project

**Code**: [AIDW] - AI Directory Website (Template)
**Template Purpose**: Reusable blueprint for launching directory website projects from niche selection to first revenue.

**Usage**: When starting a new directory project, create an instance of this template using the [AIDW-CODE] coding scheme (e.g., [AIDW-HVAC], [AIDW-PLUMB]) and customize the niche-specific information.

**Total Phases**: 6 phases, 28 stages
**Typical Duration**: 3-6 months (research to revenue)

---

## PHASE 1: DISCOVERY & NICHE VALIDATION

**Milestone**: Validate niche demand, understand decision drivers, **PROVE data is scrapeable**

**⚠️ CRITICAL GATE**: Stage 2.5 must pass before proceeding. If data can't be scraped, reject niche and restart Stage 1

### Stage 1: Niche Ideation & Selection
- **Agent**: `agent:researcher`
- **Tasks**:
  - [ ] Brainstorm 10+ potential niches (boring, high-value, fragmented markets)
  - [ ] Research search volume for top 3 niches (using SEMrush, Ahrefs)
  - [ ] Identify if niche has transparency gap or information asymmetry
  - [ ] List 20+ potential businesses/providers in the niche
- **Acceptance Criteria**: 3 validated niche options with search volume data
- **Blocks**: Stage 2
- **Output**: `ideation-summary.md`

### Stage 2: Market Demand Validation
- **Agent**: `agent:researcher`
- **Tasks**:
  - [ ] Search Reddit, TikTok, Instagram for customer pain points
  - [ ] Identify top 10 decision drivers (what do people need to decide?)
  - [ ] Find competitor directories or solutions (what exists?)
  - [ ] Interview 5-10 target customers (if possible) about their needs
  - [ ] Validate pricing/transaction value in niche
- **Acceptance Criteria**: Documented customer pain points, decision drivers, competitive landscape
- **Blocks**: Stage 2.5
- **Output**: `market-validation.md`

### Stage 2.5: Data Scraping Proof-of-Concept (CRITICAL GATE)
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 2
- **Tasks**:
  - [ ] Test scraping from Google Maps (via OutScraper) - get 50-100 sample records
  - [ ] Test scraping from 5-10 business websites in niche - verify data extractability
  - [ ] Assess data quality from sources (completeness, consistency)
  - [ ] Estimate total addressable data (how many businesses can you reach?)
  - [ ] Identify data availability gaps (what's missing? Can you fill it?)
  - [ ] Test image availability and quality from websites
  - [ ] Document scraping feasibility and challenges
  - [ ] Estimate effort/cost for full data collection
- **Acceptance Criteria**:
  - [ ] Can scrape 70%+ of target businesses
  - [ ] Data quality is sufficient (fields populated, valid contact info)
  - [ ] Images available for 50%+ of providers
  - [ ] Full dataset is technically and economically viable to collect
- **Blocks**: Stage 3 (if fails, niche is rejected)
- **GATE**: If this stage FAILS (can't get data), **DO NOT PROCEED** - reject niche and return to Stage 1
- **Output**: `data-feasibility-report.md` with proof-of-concept sample dataset

### Stage 3: Business Model Decision
- **Agent**: `agent:business-strategist`
- **Tasks**:
  - [ ] Analyze which monetization model fits best (leads, SaaS, subscriptions, ads, hybrid)
  - [ ] Identify specific B2B SaaS opportunity (if applicable)
  - [ ] Document revenue assumptions
  - [ ] Create financial projections (conservative case)
  - [ ] Define success metrics
- **Acceptance Criteria**: Clear monetization strategy with revenue projections
- **Blocks**: Phase 2 start
- **Output**: `business-model.md`

---

## PHASE 2: RESEARCH & PLANNING

**Milestone**: Deep market understanding, database design, resource identification

### Stage 4: Finalize Data Collection Strategy
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 3 (business model approved)
- **Tasks**:
  - [ ] Document all data sources identified in Stage 2.5 proof-of-concept
  - [ ] Plan full-scale data collection (build on what worked in proof-of-concept)
  - [ ] Estimate dataset size (total businesses/providers to collect)
  - [ ] Identify any additional data sources found during Stage 3
  - [ ] Plan data collection strategy (parallel scraping, batch processing, sequencing)
  - [ ] Plan image sourcing strategy (websites, stock, AI-generated as fallback)
  - [ ] Estimate timeline and resource requirements
  - [ ] Plan contingency if data sources change
- **Acceptance Criteria**: Detailed data collection plan based on validated feasibility
- **Blocks**: Stage 5
- **Output**: `data-collection-plan.md`

### Stage 5: Database Schema Design
- **Agent**: `agent:database-architect`
- **Tasks**:
  - [ ] Design data structure (what fields/attributes needed?)
  - [ ] Plan enrichment attributes (pricing, ratings, service area, hours, etc.)
  - [ ] Design for SEO optimization (URL structure, schema markup)
  - [ ] Plan filtering/sorting capabilities
  - [ ] Design scalability (how many records? growth projection?)
- **Acceptance Criteria**: Complete database schema with field definitions
- **Blocks**: Stage 6, 8
- **Output**: `database-schema.md`

### Stage 6: SEO & Keyword Strategy
- **Agent**: `agent:seo-specialist`
- **Tasks**:
  - [ ] Keyword research (location + service combinations)
  - [ ] Analyze top 20 search results for target keywords
  - [ ] Identify AI answer optimization opportunities (Google AI Overviews, Claude, etc.)
  - [ ] Plan content strategy for organic ranking
  - [ ] Design URL structure for SEO
  - [ ] Plan internal linking strategy
- **Acceptance Criteria**: Keyword strategy, content plan, SEO roadmap
- **Blocks**: Phase 3 content planning
- **Output**: `seo-strategy.md`

### Stage 7: SaaS Feature Definition (if applicable)
- **Agent**: `agent:product-manager`
- **Dependency**: Blocked by Stage 3
- **Tasks**:
  - [ ] Define core SaaS features (what problem does it solve?)
  - [ ] Create feature MVP (minimum viable product)
  - [ ] Estimate development effort
  - [ ] Design pricing strategy
  - [ ] Plan go-to-market for SaaS
- **Acceptance Criteria**: SaaS feature spec, pricing, GTM plan
- **Blocks**: Development phases
- **Output**: `saas-specification.md`

### Stage 8: Resource Preparation
- **Agent**: `agent:project-manager`
- **Dependency**: Blocked by Stage 5
- **Tasks**:
  - [ ] Create repository structure
  - [ ] Set up database (local or cloud)
  - [ ] Prepare OutScraper templates
  - [ ] Prepare Crawl4AI configurations
  - [ ] Create data cleaning scripts/templates
  - [ ] Document all tools and access
- **Acceptance Criteria**: Working repository, scrapers configured, tools ready
- **Blocks**: Phase 3 execution
- **Output**: Repository structure created

---

## PHASE 3: DATA ACQUISITION

**Milestone**: Collect raw data, initial cleaning, data preparation

### Stage 9: Initial Data Scraping
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 8
- **Tasks**:
  - [ ] Run OutScraper for Google Maps data
  - [ ] Scrape business websites for detailed info
  - [ ] Collect initial dataset (all providers in niche)
  - [ ] Log data source and timestamp
  - [ ] Export to CSV/database
- **Acceptance Criteria**: Raw dataset collected, 80%+ coverage of target providers
- **Blocks**: Stage 10
- **Output**: `raw-data/providers.csv`

### Stage 10: Initial Data Cleaning (Part 1)
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 9
- **Tasks**:
  - [ ] Remove obvious duplicates
  - [ ] Remove invalid entries (closed businesses, fake listings)
  - [ ] Standardize formats (phone, address, hours)
  - [ ] Remove junk/spam entries
  - [ ] Document cleaning rules used
- **Acceptance Criteria**: Dataset with 95%+ valid entries
- **Blocks**: Stage 11
- **Output**: `cleaned-data/providers-cleaned.csv`

### Stage 11: Data Verification & Enrichment Research
- **Agent**: `agent:researcher`
- **Dependency**: Blocked by Stage 10
- **Tasks**:
  - [ ] Deep dive on data quality issues
  - [ ] Verify critical fields (phone, address, services)
  - [ ] Identify "quality" or "premium" providers (luxury restroom example)
  - [ ] Crawl websites for missing data using Crawl4AI
  - [ ] Document any data quality patterns
- **Acceptance Criteria**: Verified accuracy for 95%+ of entries
- **Blocks**: Stage 12
- **Output**: `verification-report.md`

### Stage 12: Image Collection
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 11
- **Tasks**:
  - [ ] Scrape images from provider websites
  - [ ] Download high-quality images (minimum 500x500px)
  - [ ] Organize by provider ID
  - [ ] Use Claude Vision to score image quality
  - [ ] Select top 2-3 images per provider
  - [ ] Document image rights/source
  - [ ] Fallback: Use stock images or AI-generated for missing
- **Acceptance Criteria**: 70%+ providers have quality images with rights verified
- **Blocks**: Stage 13
- **Output**: `images/` directory organized by provider

---

## PHASE 4: DATA ENRICHMENT & PREPARATION

**Milestone**: Enrich data, add attributes, quality signals, prepare for website

### Stage 13: Data Enrichment (Attributes & Attributes)
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 12
- **Tasks**:
  - [ ] Add pricing information (if available)
  - [ ] Add service/product categories
  - [ ] Add geographic/service area data
  - [ ] Add quality signals (ratings, reviews, certifications)
  - [ ] Add hours of operation
  - [ ] Add contact methods (phone, email, website)
  - [ ] Calculate computed fields (distance, availability, etc.)
- **Acceptance Criteria**: Database populated with enriched attributes
- **Blocks**: Stage 14, 15
- **Output**: `enriched-data/providers-enriched.csv`

### Stage 14: Review Aggregation
- **Agent**: `agent-researcher`
- **Dependency**: Blocked by Stage 13
- **Tasks**:
  - [ ] Scrape/aggregate existing reviews (Google, Yelp, industry sites)
  - [ ] Standardize review data
  - [ ] Calculate average ratings
  - [ ] Extract key review insights
  - [ ] Document review sources
- **Acceptance Criteria**: Review data integrated into database for 50%+ providers
- **Blocks**: Stage 15
- **Output**: `enriched-data/reviews-aggregated.csv`

### Stage 15: AI-Powered Data Quality Check
- **Agent**: `agent:data-engineer`
- **Dependency**: Blocked by Stage 14
- **Tasks**:
  - [ ] Use AI to identify inconsistencies
  - [ ] Validate data against schema
  - [ ] Flag suspicious or low-quality entries
  - [ ] Use Claude Vision to verify images
  - [ ] Generate quality score per record
- **Acceptance Criteria**: Data quality report with scores, 95%+ passing quality threshold
- **Blocks**: Stage 16
- **Output**: `quality-report.md`

### Stage 16: Final Data Validation
- **Agent**: `agent:human`
- **Dependency**: Blocked by Stage 15
- **Tasks**:
  - [ ] Manual spot-check of 50+ random entries
  - [ ] Verify critical data (contact info works, businesses are real)
  - [ ] Flag any remaining issues
  - [ ] Approve data for publication
- **Acceptance Criteria**: Human sign-off on data quality
- **Blocks**: Phase 5 development
- **Output**: Data approved for use

---

## PHASE 5: BUILD & DEVELOPMENT

**Milestone**: Database implementation, website build, SEO optimization

### Stage 17: Database Implementation
- **Agent**: `agent:developer`
- **Dependency**: Blocked by Stage 16
- **Tasks**:
  - [ ] Set up production database (PostgreSQL, MongoDB, etc.)
  - [ ] Implement schema with indexing
  - [ ] Upload enriched dataset
  - [ ] Set up backup/recovery procedures
  - [ ] Implement data validation at DB level
  - [ ] Test query performance
- **Acceptance Criteria**: Database live and optimized, can handle queries efficiently
- **Blocks**: Stage 18
- **Output**: Production database running

### Stage 18: Website Development (Backend)
- **Agent**: `agent:developer`
- **Dependency**: Blocked by Stage 17
- **Tasks**:
  - [ ] Set up web framework (Next.js, Django, etc.)
  - [ ] Build database API/queries
  - [ ] Implement filtering/sorting
  - [ ] Build search functionality
  - [ ] Implement pagination
  - [ ] Set up user authentication (if needed)
  - [ ] Build admin interface for data management
- **Acceptance Criteria**: API fully functional, all queries working
- **Blocks**: Stage 19
- **Output**: Backend API running

### Stage 19: Website Development (Frontend)
- **Agent**: `agent:developer`
- **Dependency**: Blocked by Stage 18
- **Tasks**:
  - [ ] Design UI/UX (directory listing, detail pages, filters)
  - [ ] Build responsive design (mobile-first)
  - [ ] Implement search interface
  - [ ] Build provider detail pages (rich content)
  - [ ] Implement filtering/sorting UI
  - [ ] Add sharing/social features
  - [ ] Build contact/lead generation forms
- **Acceptance Criteria**: Website fully functional and responsive
- **Blocks**: Stage 20
- **Output**: Website live

### Stage 20: SEO Implementation
- **Agent**: `agent:seo-specialist`
- **Dependency**: Blocked by Stage 19
- **Tasks**:
  - [ ] Implement structured data (schema.org)
  - [ ] Implement meta tags (title, description per page)
  - [ ] Create SEO-friendly URLs
  - [ ] Implement Open Graph tags (social sharing)
  - [ ] Create sitemap and robots.txt
  - [ ] Set up Google Search Console
  - [ ] Optimize page speed
  - [ ] Implement AI answer optimizations
- **Acceptance Criteria**: SEO audit passing, indexed in search engines
- **Blocks**: Phase 6
- **Output**: SEO implementation complete

### Stage 21: SaaS Development (if applicable)
- **Agent**: `agent:developer`
- **Dependency**: Blocked by Stage 18
- **Tasks**:
  - [ ] Build SaaS MVP (MVP features from Stage 7)
  - [ ] Implement authentication and user management
  - [ ] Build billing/payment integration
  - [ ] Create dashboard for business users
  - [ ] Implement usage tracking/analytics
  - [ ] Set up customer support tools
- **Acceptance Criteria**: SaaS MVP functional and testable
- **Blocks**: Stage 25
- **Output**: SaaS application ready for beta testing

### Stage 22: Testing & QA
- **Agent**: `agent:qa-tester`
- **Dependency**: Blocked by Stage 20, 21 (if SaaS)
- **Tasks**:
  - [ ] Test all directory features (search, filters, detail pages)
  - [ ] Test SaaS features (if applicable)
  - [ ] Test on mobile devices
  - [ ] Test form submissions and lead capture
  - [ ] Test performance under load
  - [ ] Security testing (SSL, data protection)
  - [ ] Cross-browser testing
- **Acceptance Criteria**: No critical bugs, all tests passing
- **Blocks**: Phase 6
- **Output**: QA report

---

## PHASE 6: LAUNCH & MARKETING

**Milestone**: Launch website, implement growth strategy, generate first revenue

### Stage 23: Pre-Launch Preparation
- **Agent**: `agent:project-manager`
- **Dependency**: Blocked by Stage 22
- **Tasks**:
  - [ ] Create launch checklist
  - [ ] Set up analytics (Google Analytics, custom tracking)
  - [ ] Set up monitoring/alerts
  - [ ] Create documentation (for users, for maintenance)
  - [ ] Plan launch announcement
  - [ ] Prepare customer support setup
- **Acceptance Criteria**: Launch ready, all systems prepared
- **Blocks**: Stage 24
- **Output**: Launch checklist completed

### Stage 24: Soft Launch & Initial Testing
- **Agent**: `agent:project-manager`
- **Dependency**: Blocked by Stage 23
- **Tasks**:
  - [ ] Launch to limited audience (friends, beta users)
  - [ ] Gather feedback
  - [ ] Monitor for bugs/issues
  - [ ] Fix critical issues found
  - [ ] Validate functionality in production
  - [ ] Test lead generation flow
- **Acceptance Criteria**: Soft launch successful, ready for public launch
- **Blocks**: Stage 25
- **Output**: Feedback report, bug fixes applied

### Stage 25: Public Launch
- **Agent**: `agent:project-manager`
- **Dependency**: Blocked by Stage 24
- **Tasks**:
  - [ ] Deploy to production (full public)
  - [ ] Submit to search engines
  - [ ] Submit sitemap to Google Search Console
  - [ ] Monitor uptime and errors
  - [ ] Track initial metrics (traffic, conversions)
- **Acceptance Criteria**: Website live and publicly accessible
- **Blocks**: Stage 26, 27
- **Output**: Launch log, initial metrics

### Stage 26: Organic Growth & SEO Optimization
- **Agent**: `agent:seo-specialist`
- **Dependency**: Blocked by Stage 25
- **Tasks**:
  - [ ] Monitor keyword rankings
  - [ ] Optimize for long-tail keywords
  - [ ] Build internal linking strategy
  - [ ] Create content (blog posts, guides, FAQs)
  - [ ] Monitor organic traffic growth
  - [ ] Implement link-building strategy
  - [ ] Optimize for AI answers (monitor appearance in Google AI, Claude, etc.)
- **Acceptance Criteria**: Organic traffic growing month-over-month, keywords ranking
- **Blocks**: Stage 28
- **Output**: Monthly SEO report

### Stage 27: SaaS Launch & Customer Acquisition (if applicable)
- **Agent**: `agent:business-strategist`
- **Dependency**: Blocked by Stage 25
- **Tasks**:
  - [ ] Identify early customers from directory users
  - [ ] Create SaaS sales pitch/marketing
  - [ ] Outreach to target businesses
  - [ ] Close first 5-10 customers
  - [ ] Gather feedback for improvements
  - [ ] Refine product based on real usage
- **Acceptance Criteria**: First 5+ SaaS customers, revenue generated
- **Blocks**: Stage 28
- **Output**: Customer list, revenue tracking started

### Stage 28: Revenue Tracking & Optimization
- **Agent**: `agent:business-strategist`
- **Dependency**: Blocked by Stages 26, 27
- **Tasks**:
  - [ ] Track first revenue (leads, SaaS subscriptions, ads, etc.)
  - [ ] Calculate CAC (customer acquisition cost)
  - [ ] Calculate LTV (lifetime value)
  - [ ] Identify highest-performing channels
  - [ ] Plan next growth initiatives
  - [ ] Document what's working
- **Acceptance Criteria**: First dollar/euro earned, metrics tracked, growth plan for next phase
- **Output**: Revenue tracking dashboard, growth strategy

---

## PARALLEL EXECUTION OPPORTUNITIES

**Phase 1 is SEQUENTIAL (critical gates):**
- Stage 1 → 2 → 2.5 (GATE) → 3 must run in order
- If Stage 2.5 FAILS, restart at Stage 1 with different niche
- No parallelization until niche is validated AND data is proven scrapeable

**Later phases can run in parallel (after their blockers):**
- Stages 4, 5, 6, 7, 8: Can start in parallel after Stage 3 (all blocked by Stage 3)
- Stages 17, 18: Database implementation + Website backend (sequential dependency)
- Stages 19, 20, 21: Frontend + SEO + SaaS dev (all can start after Stage 18)
- Stages 26, 27: SEO growth + SaaS launch (both after Stage 25)

---

## AGENT ROLE DEFINITIONS

| Role | Responsibilities | Expertise Required |
|------|-----------------|-------------------|
| `agent:researcher` | Market research, validation, data verification, review aggregation | Research, data analysis, market knowledge |
| `agent:business-strategist` | Business model design, SaaS strategy, customer acquisition, revenue tracking | Business strategy, product-market fit, sales |
| `agent:database-architect` | Database schema design, data structure planning, scalability | Database design, SQL/NoSQL, optimization |
| `agent:seo-specialist` | Keyword research, SEO strategy, site optimization, AI answer optimization | SEO, SEM, content strategy, technical SEO |
| `agent:product-manager` | Feature definition, product roadmap, specifications | Product management, user experience, requirements |
| `agent:project-manager` | Planning, setup, coordination, launch management | Project management, coordination |
| `agent:data-engineer` | Data scraping, cleaning, enrichment, quality checks | ETL, data pipelines, SQL, scripting |
| `agent:developer` | Backend/frontend development, database implementation, API building | Full-stack development, web frameworks |
| `agent:qa-tester` | Testing, quality assurance, bug finding | QA, testing strategies, documentation |
| `agent:human` | Manual review, decision-making, approval | Critical thinking, domain knowledge |

---

## OUTPUT STRUCTURE

When creating a real project from this template, organize outputs:

```
/[niche-name]-directory/
├── README.md
├── /research/
│   ├── ideation-summary.md
│   ├── market-validation.md
│   ├── business-model.md
│   ├── data-sources.md
│   └── verification-report.md
├── /planning/
│   ├── database-schema.md
│   ├── seo-strategy.md
│   └── saas-specification.md (if applicable)
├── /data/
│   ├── raw-data/
│   │   └── providers.csv
│   ├── cleaned-data/
│   │   └── providers-cleaned.csv
│   ├── enriched-data/
│   │   ├── providers-enriched.csv
│   │   └── reviews-aggregated.csv
│   ├── images/
│   │   └── [provider-id]/
│   └── quality-report.md
├── /website/
│   ├── backend/
│   ├── frontend/
│   └── seo-config/
├── /saas/
│   └── [SaaS application code]
├── /launch/
│   ├── launch-checklist.md
│   ├── launch-log.md
│   └── initial-metrics.md
└── /tracking/
    ├── revenue-log.md
    └── growth-strategy.md
```

---

## USAGE NOTES

- **Create niche-specific instance** from this template for each new directory project
- **⚠️ CRITICAL**: Stage 2.5 (Data Scraping Proof-of-Concept) is a hard gate
  - If it FAILS (can't get data), REJECT the niche and return to Stage 1
  - Don't waste time on planning if data isn't available
  - This saves weeks of wasted effort
- **Customize decision criteria** in early stages based on research
- **Adjust scope** if niche doesn't support full SaaS model (skip Stages 7, 21, 27)
- **Timeline is flexible** - some projects may move faster, others slower
- **Human approval points** at Stage 16 and Stage 24 ensure quality gates
- **All outputs documented** in repository for knowledge preservation
- **Keep proof-of-concept dataset** from Stage 2.5 - reuse it for full data collection in Phase 3
