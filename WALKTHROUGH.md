# Resume PDF Generation Walkthrough

## Issue: BasicTeX Installation

The `pdflatex` command is not found because BasicTeX is installed but the package hasn't been fully set up yet.

## Solution Steps

### Step 1: Install BasicTeX Package (Requires Password)

**Option A - Quick Install (Recommended):**
```bash
# Run this command and enter your password when prompted
sudo installer -pkg /opt/homebrew/Caskroom/basictex/2025.0308/mactex-basictex-20250308.pkg -target /
```

**Option B - Reinstall via Brew:**
```bash
# This will also prompt for your password
brew reinstall basictex
```

### Step 2: Update PATH

After installation, reload your shell environment:

```bash
# Method 1: Run path helper
eval "$(/usr/libexec/path_helper)"

# Method 2: Or restart your terminal completely
```

### Step 3: Verify Installation

Check that pdflatex is now available:

```bash
which pdflatex
pdflatex --version
```

### Step 4: Compile Resume

Once pdflatex is working:

```bash
# Navigate to your resume directory
cd /Volumes/WasimSSD/aahanatech/resume

# Compile the resume
pdflatex resume.tex

# If there are warnings about packages, run again:
pdflatex resume.tex
```

## Alternative: Online LaTeX Editor

If you prefer not to install BasicTeX locally, you can use **Overleaf**:

1. Go to https://www.overleaf.com
2. Create a free account
3. Upload `resume.tex`
4. Click "Recompile" to generate PDF
5. Download the PDF

## Updated Resume Styling

The `resume.tex` file has been updated with:

- **Clean, professional layout** matching the reference PDF style
- **Proper section formatting** with bold headers and rules
- **Consistent spacing** and typography
- **Hyperlinked contact information** (email, LinkedIn, GitHub)
- **Two-page optimized layout** for better readability

### Key Changes Made:

1. Switched from `moderncv` class to standard `article` class for cleaner look
2. Removed fancy fonts and icons for ATS compatibility
3. Improved job entry formatting with consistent date ranges
4. Reorganized skills section for better scannability
5. Added proper page breaks and spacing

## Troubleshooting

### Error: "pdflatex: command not found"

**Fix:** Run the install command from Step 1 above and restart your terminal.

### Error: "File moderncv.cls not found"

**Fix:** The updated `resume.tex` no longer uses `moderncv`. If you have an old version, use the new one that uses standard `article` class.

### Error: "Missing packages"

BasicTeX is a minimal distribution. If you get missing package errors:

```bash
# Use tlmgr to install missing packages
sudo tlmgr install <package-name>

# Or switch to full MacTeX (much larger install)
brew install --cask mactex
```

## Generated PDF Location

After successful compilation, the PDF will be created as:
```
/Volumes/WasimSSD/aahanatech/resume/resume.pdf
```
