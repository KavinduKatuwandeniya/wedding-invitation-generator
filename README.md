# Wedding Invitation Generator — Vercel

This version uses the current zero-configuration FastAPI deployment model.

## Structure

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
├── .gitignore
└── README.md
```

There is intentionally no `vercel.json`.

## Important

Copy your full Rockwell font to:

```text
fonts/ROCK.TTF
```

## Local test

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
pip install "fastapi[standard]"
fastapi dev api/index.py
```

Open:

```text
http://127.0.0.1:8000/
```

You can also use:

```powershell
vercel dev
```

## Deploy

From the project root:

```powershell
vercel login
vercel link
vercel deploy --prod
```

Or connect the GitHub repository from the Vercel dashboard.

## Input modes

### Single Name

Enter a name and download one PDF.

### Excel

Upload an `.xlsx` or `.xlsm` file with names in column A starting at A2. A ZIP containing one PDF per name is returned.

## PDF formatting

- Rockwell
- 10 pt
- `#765830`
- 84/1000 em letter spacing
- centered at X 199.001
- baseline Y 134.0
- dotted line Y 138.5

## Privacy

Uploaded files are processed for the generation request and are not intentionally persisted by the application.
