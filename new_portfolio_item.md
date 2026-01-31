# How to Add New Portfolio Items

## Step 1: Add Your PDF File

Place your PDF in the `assets/portfolio/` folder:

```
assets/portfolio/your-new-file.pdf
```

---

## Step 2: Add the Item to portfolio.html

Open `portfolio.html` and find the `portfolioItems` array (around line 389). Add a new object:

```javascript
{
    id: 4,  // Increment the ID (next available number)
    title: 'Your Project Title',
    category: 'simulation',  // Options: 'simulation', 'documentation', 'design'
    date: '2026-02-05',  // Format: YYYY-MM-DD
    description: 'Brief description of what this project is about',
    thumbnail: 'assets/portfolio/your-new-file.pdf',  // Same as fileUrl for PDFs
    fileUrl: 'assets/portfolio/your-new-file.pdf',
    fileType: 'pdf',  // Important! This enables PDF preview
    tags: ['Tag1', 'Tag2', 'Tag3']  // Relevant keywords
},
```

---

## Example - Adding a Differential Amplifier

### 1. Put the PDF at:
```
assets/portfolio/diff-amp.pdf
```

### 2. Add to the array (after the last item, before the closing `];`):

```javascript
{
    id: 4,
    title: 'Differential Amplifier Design',
    category: 'simulation',
    date: '2026-02-10',
    description: 'LTspice simulation of a differential pair with active load',
    thumbnail: 'assets/portfolio/diff-amp.pdf',
    fileUrl: 'assets/portfolio/diff-amp.pdf',
    fileType: 'pdf',
    tags: ['Differential', 'Amplifier', 'LTspice']
},
```

### 3. Push to GitHub:

```bash
git add -A
git commit -m "Add differential amplifier to portfolio"
git push
```

---

## Field Reference

| Field | Description | Example |
|-------|-------------|---------|
| `id` | Unique number (increment from last) | `4` |
| `title` | Project name | `'Differential Amplifier Design'` |
| `category` | Filter category | `'simulation'`, `'documentation'`, `'design'` |
| `date` | Date in YYYY-MM-DD format | `'2026-02-10'` |
| `description` | Brief summary | `'LTspice simulation of...'` |
| `thumbnail` | Path to PDF (shows preview) | `'assets/portfolio/file.pdf'` |
| `fileUrl` | Path to PDF (for download) | `'assets/portfolio/file.pdf'` |
| `fileType` | Must be `'pdf'` for PDF files | `'pdf'` |
| `tags` | Array of keywords | `['MOSFET', 'Amplifier']` |

---

## Quick Checklist

- [ ] PDF file placed in `assets/portfolio/`
- [ ] Unique `id` number assigned
- [ ] `fileType: 'pdf'` included
- [ ] `thumbnail` and `fileUrl` both point to the PDF
- [ ] Comma after the closing `}` (except for the last item in array)
- [ ] Changes pushed to GitHub
