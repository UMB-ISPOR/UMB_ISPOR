# UMB ISPOR Website Update Guide

## 1. Local Setup
- Clone the repository:  
  ```bash
  git clone https://github.com/UMB-ISPOR/UMB_ISPOR.git
  cd UMB_ISPOR
  ```
- Install R and RStudio if not already installed.  
- Install required R packages:  
  ```r
  install.packages(c("rmarkdown", "knitr"))
  ```

## Before Updating .Rmd Files
Please maintain:
1. ISPOR Presentation List in Google Drive: https://docs.google.com/spreadsheets/d/1zEE23AcJEGOqL6qvhd-17jQMSaH0IKhHYKXVdbjoAtI/edit?usp=sharing 
2. ISPOR Award tracking sheet in Google Drive: https://docs.google.com/spreadsheets/d/1GaMJ7NHEiSshsx2rNeE9Joz6fuHVNLQqoAduur7ovdc/edit?usp=sharing
3. ISPOR Student Publication list on SharePoint by running:  
   “Shared Documents - RX-SO-ISPOR/Website/ISPOR member pubmed query/ISPOR member pubmed query.R”  
   and copy the output file **`UMB_ISPOR_Publications.csv`** to this GitHub repository.  

## 2. Update Content
Edit the `.Rmd` files in the repo root:
- `index.Rmd` → About page
- `ISPOR.Rmd` → ISPOR Student Network
- `team.Rmd` → Executive Board
- `table.Rmd` → Achievements/Publications
- `gallery.Rmd` → Gallery
- `follow.Rmd` → Social links

Update text, bios, and photos (store images in `headshot/`).

## 3. Update Navigation
- Navbar is defined in `_site.yml`.  
- Change text or add new pages under `navbar > left/right`.  
- Ensure links match page filenames.

## 4. Rebuild the Site
In RStudio, run:  
```r
source("Render all.R")
```
This regenerates all `.html` files and supporting `site_libs/`.

Optional: set `output_dir: "docs"` in `_site.yml` if publishing from `/docs`.

## 5. Deploy to GitHub Pages
- Commit and push changes:  
  ```bash
  git add .
  git commit -m "Update site"
  git push
  ```
- In GitHub repo → **Settings → Pages**:  
  - Source: `main` branch  
  - Folder: `/` (root) or `/docs` if using `output_dir`.  

Site is live at: <https://umb-ispor.github.io/UMB_ISPOR/>

## 6. Maintenance Notes
- `_config.yml` controls Jekyll (theme, baseurl). Leave unless URLs/theme change.  
- `style.css` customizes colors/fonts.  
- `site_libs/` is auto-generated, don’t edit manually.  
- Fix typo in navbar title: "Chpater" → "Chapter".  

## 7. Annual Update Checklist
- [ ] Update Executive Board info in `team.Rmd`.  
- [ ] Add new awards & publications in `table.Rmd`.  
- [ ] Refresh photos in `gallery.Rmd` and `headshot/`.  
- [ ] Update social links in `follow.Rmd`.  
- [ ] Update About page (`index.Rmd`) if needed.  
- [ ] Run `source("Render all.R")` and preview locally.  
- [ ] Commit + push changes.  
- [ ] Verify site loads at <https://umb-ispor.github.io/UMB_ISPOR/>.  
