# Audit template

## How to generate a report
1. Export md to epub html via https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced VS Code extension
2. Add `class="pagebreak"` to html elements where page break is necessary
3. Add css for page counter and visual additions:
```css
@media print {
    /* add page numbers */
    @page {
        @bottom-center {
            counter-increment: page;
            content: counter(page, decimal);
        }
        @top-center {
            content: "";
        }
    }
    /* code styles */
    html body pre {
        page-break-inside: auto;
    }
    html body pre code {
        text-wrap: wrap;
    }
}
``` 
4. Save as PDF via chrome print tool
5. Prepare front page:
    1) Update `front_page_template.kra` with protocol details
    2) Export `front_page_template.kra` to `png`
    3) Convert `front_page_template.png` to `pdf` via https://www.ilovepdf.com/jpg_to_pdf
6. Merge `front_page_template.pdf` and `REPORT.pdf` via https://www.ilovepdf.com/merge_pdf
