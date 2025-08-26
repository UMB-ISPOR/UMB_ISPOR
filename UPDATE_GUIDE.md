# UMB ISPOR Website Update Guide

## 1. Local Setup
- Clone the repository:  
  ```bash
  git clone https://github.com/umb-ispor/UMB_ISPOR.git
  cd UMB_ISPOR
  ```
- Install R and RStudio if not already installed.  
- Install required R packages:  
  ```r
  install.packages(c("rmarkdown", "knitr"))
  ```

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
- [ ] Run `rmarkdown::render_site()` and preview locally.  
- [ ] Commit + push changes.  
- [ ] Verify site loads at <https://umb-ispor.github.io/UMB_ISPOR/>.  
