# Wedding Invitation Generator

A mobile-friendly Vercel web app for generating personalized wedding invitation PDFs.

## Two input modes

### Single Name

Enter a guest name in the text box.

Example:

`Mr. Kulunu Weerasoory`

The app generates one PDF immediately.

### Excel List

Upload an `.xlsx` or `.xlsm` file.

Format:

| A |
|---|
| Name |
| Mr. Kulunu Weerasoory |
| Mr. John Perera |
| Ms. Jane Perera |

Names are read from A2 downward and converted to ALL CAPS.

The app generates one PDF for each name and returns a ZIP file.

## Project structure

```text
wedding-invitation-generator/
├── api/
│   └── index.py
├── public/
│   └── index.html
├── fonts/
│   └── ROCK.TTF
├── requirements.txt
├── pyproject.toml
├── vercel.json
├── .gitignore
└── README.md
```

## Important: Rockwell font

Place the full Windows Rockwell font file here:

```text
fonts/ROCK.TTF
```

Do not use a subsetted Rockwell font extracted from the PDF.

The generator uses:

- Rockwell
- 10 pt
- `#765830`
- 84/1000 em letter spacing
- centered name
- dotted line underneath the name

## Local setup

Create and activate a virtual environment:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Install Vercel CLI:

```powershell
npm install -g vercel
```

Run locally:

```powershell
vercel dev
```

Open:

```text
http://localhost:3000
```

## Deploy

Login:

```powershell
vercel login
```

Deploy preview:

```powershell
vercel
```

Deploy production:

```powershell
vercel --prod
```

## Mobile support

The frontend is responsive and designed for phones, tablets, and desktop browsers.

It supports:

- iPhone Safari
- Android Chrome
- tablet browsers
- desktop browsers

The file controls use the native mobile file picker, so users can select files from their phone.

## Files processed

The invitation PDF template and Excel file are uploaded only for the generation request. The application does not intentionally store them in a database.

## Important Vercel limitation

For large guest lists or large PDFs, serverless request/response limits can become relevant. This design is intended for normal wedding invitation templates and reasonably sized guest lists.

If the guest list becomes very large, the architecture should be changed to use object storage/background processing.

## Private wedding use

If the URL will be shared publicly, consider adding authentication before using it for real guest data.

## License / assets

Make sure you have appropriate rights to use the invitation artwork and Rockwell font in your deployment.
