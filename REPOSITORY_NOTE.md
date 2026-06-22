# Repository Note: Personal Website - Yalemzewod Gelaw

## Overview
This is the source code for a **professional personal website and blog** dedicated to data science, statistical analysis, and epidemiology. The site serves as a platform for sharing knowledge about data manipulation, visualization, and practical applications in public health using R and Python.

**Live Site:** [https://yalemzewodgelaw.com](https://yalemzewodgelaw.com)

## Repository Details
- **Owner:** Yalemzewod Gelaw
- **Repository:** yalemgelaw.github.io
- **Created:** April 3, 2023
- **Last Updated:** June 3, 2026
- **Status:** Active
- **Repository Size:** ~49 MB

## Technology Stack

### Primary Technologies
- **JavaScript** (86.5%) - Interactive elements and site functionality
- **CSS** (8.7%) - Styling and responsive design
- **Lua** (2.4%) - Configuration scripts
- **TeX** (1.2%) - Mathematical typesetting
- **Other** (1.2%) - Supporting files

### Build Framework
- **Quarto** - Literate programming and site generation
- **R/R Markdown** - Document processing and code execution
- **Jekyll/GitHub Pages** - Static site hosting

## Content Structure

### Core Pages
1. **Home** (`index.qmd`) - Professional introduction and welcome
2. **About** (`about.qmd`) - Professional background and experience
3. **CV & Resume** (`CV/`) - Curriculum vitae and professional credentials
4. **Publications** (`publications.qmd`) - Research publications and articles
5. **Grants & Awards** (`grantsandawards.qmd`) - Funding and recognitions
6. **Workshops & Presentations** (`workshopsandpresentations.qmd`) - Speaking engagements
7. **Skills** (`skills.qmd`) - Technical and domain expertise
8. **Tutorials & Posts** (`posts/`) - Blog content and educational resources

### Featured Blog Posts
- **"Mastering RStudio: A Beginner's Guide"** - Essential RStudio techniques, operators, data types, and data import
- **"Data Manipulation in dplyr"** - Advanced data cleaning and transformation using tidyverse ecosystem

## Key Features

### Navigation & Connectivity
✓ Multi-page navigation with search functionality  
✓ Social media integration:
- Twitter/X (@yalassefa)
- GitHub (Yalemzewod)
- LinkedIn
- YouTube (@yz1121)
- ORCID (0000-0002-5338-586X)

✓ Responsive design (light/dark theme support)  
✓ Table of contents for easy navigation  
✓ GitHub integration (source code, issue tracking)

### Blog Capabilities
- Rich code highlighting with multiple language support
- Code folding and code tools
- Interactive content
- Searchable post archive
- Categories and tags
- Date-based organization

## Configuration Files

### `_quarto.yml`
Main site configuration:
```yaml
- Project type: website
- Site title: "Yalemzewod A Gelaw"
- Theme: Flatly (light) & Darkly (dark)
- Font: Nunito
- Search enabled
- Preview settings (port: 4200)
```

### `_publish.yml`
Publishing configuration for deployment

### `netlify.toml`
Netlify hosting configuration

### `styles.scss`
Custom SCSS styling

## Sample Showcase: Blog Post Structure

### Example: RStudio Guide Post

```markdown
---
title: "Mastering RStudio: A Beginner's Guide"
description: |
  Essential Techniques and Tools for Effective R Programming
author: 
  - name: Yalemzewod Gelaw
    url: https://yalemzewodgelaw.com/
date: 2024-05-24
image: "media/rstudio.png"
categories: [RStudio, R]
toc: true
---
```

### Content Sections Covered
1. **Overview of RStudio** - Layout and panels
2. **Project Management** - Organizing R projects
3. **Working Directory** - File and folder management
4. **R Operators** - Arithmetic, logical, and pipe operators
5. **Data Types** - Numeric, character, logical, integer, complex
6. **Data Structures** - Vectors, lists, matrices, data frames, factors
7. **Package Management** - Installation and loading
8. **Data Import** - CSV, Excel, Stata files
9. **Data Exploration** - head(), tail(), str(), glimpse()

### Example: Data Manipulation in dplyr Post

```r
# Comprehensive data cleaning workflow
clean_routine_data <- routine_data %>% 
  # Select relevant columns
  dplyr::select(region, zone, district, Month, Year,
         test_performed, confirmed_all,
         confirmed_u5, confirmed_5_14, confirmed_15) %>% 
  # Remove missing values
  drop_na(test_performed, confirmed_all,
         confirmed_u5, confirmed_5_14, confirmed_15) %>% 
  # Data quality checks
  filter(test_performed > confirmed_all) %>% 
  # Correct data entry errors
  mutate(region = case_when(
    region == 'Sou' ~ 'South Western Ethiopia',
    TRUE ~ region)) %>%
  # Create date variable
  mutate(date_reported = make_date(year = Year, month = Month)) %>%
  # Aggregate data
  group_by(region, zone, district) %>% 
  summarise(across(starts_with("confirmed"), sum, na.rm = TRUE))
```

## dplyr Functions Demonstrated
- `select()` - Column selection
- `filter()` - Row filtering
- `mutate()` - Creating/modifying variables
- `rename()` - Column renaming
- `distinct()` - Remove duplicates
- `arrange()` - Sorting
- `group_by()` & `summarise()` - Aggregation
- `pivot_wider()` & `pivot_longer()` - Data reshaping
- `join()` functions - Data merging

## Educational Focus
This repository demonstrates:
- **Data Science Workflow** - Import → Clean → Analyze → Visualize
- **Epidemiological Analysis** - Public health data processing
- **R Programming** - Beginner to intermediate skills
- **Best Practices** - Reproducible research and documentation
- **Real-World Applications** - Using DHIS2 and health surveillance data

## Technical Highlights

### Development Features
- Version control with Git
- Quarto document rendering
- Automated build and deployment
- Search functionality
- Responsive web design
- Social media integration

### Data Topics Covered
- Routine malaria surveillance data (DHIS2)
- Data cleaning and standardization
- Long/wide format transformations
- Aggregation and summarization
- Date handling and manipulation
- Missing value management

## Use Cases
✓ Learning R and RStudio fundamentals  
✓ Understanding dplyr data manipulation  
✓ Epidemiological data processing workflows  
✓ Building responsive personal websites with Quarto  
✓ Creating reproducible data analysis documents  
✓ Publishing research and professional content  

## Getting Started
1. Visit the live site at https://yalemzewodgelaw.com
2. Browse blog posts and tutorials
3. Access the curriculum vitae
4. Explore technical skills and expertise
5. Follow on social media for updates

## Content Categories
- **RStudio** - IDE tutorials and tips
- **R** - Programming language tutorials
- **Data Management** - Data cleaning and transformation
- **Statistics** - Statistical analysis methods
- **Epidemiology** - Public health applications
- **Visualization** - Data visualization techniques
- **Python** - Python data science content

---
*A comprehensive professional portfolio showcasing expertise in data science, statistical analysis, and epidemiological research through practical tutorials and real-world examples.*
