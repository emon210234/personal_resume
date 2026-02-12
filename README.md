# Personal Resume - LaTeX CV Template

A professional resume/CV template using LaTeX and the **Twenty Seconds CV** template style.

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Step-by-Step Setup Guide](#step-by-step-setup-guide)
  - [Option 1: MiKTeX + TeXStudio (Windows)](#option-1-miktex--texstudio-windows)
  - [Option 2: Overleaf (Online)](#option-2-overleaf-online)
  - [Option 3: TeX Live (Linux/macOS)](#option-3-tex-live-linuxmacos)
- [Compiling the Resume](#compiling-the-resume)
- [Customizing Your Resume](#customizing-your-resume)
- [Troubleshooting](#troubleshooting)
- [File Structure](#file-structure)

---

## Prerequisites

This template requires a working LaTeX installation with the following packages:
- `ClearSans` (font)
- `tikz` (graphics)
- `textpos` (positioning)
- `hyperref` (links)
- `marvosym` (icons)

Most TeX distributions include these packages by default, or will auto-install them on first use.

---

## Step-by-Step Setup Guide

### Option 1: MiKTeX + TeXStudio (Windows)

This is the recommended setup for Windows users who prefer a local installation.

#### Step 1: Install MiKTeX

1. Download MiKTeX from [https://miktex.org/download](https://miktex.org/download)
2. Run the installer and follow the prompts
3. **Important**: During installation, select **"Yes"** for "Install missing packages on-the-fly"
4. Complete the installation

#### Step 2: Install TeXStudio

1. Download TeXStudio from [https://www.texstudio.org/](https://www.texstudio.org/)
2. Run the installer and follow the prompts
3. Complete the installation

#### Step 3: Configure TeXStudio

1. Open TeXStudio
2. Go to **Options** → **Configure TeXStudio**
3. In the left panel, click **Build**
4. Ensure **Default Compiler** is set to **PdfLaTeX**
5. Click **OK**

#### Step 4: Open the Project

1. Download or clone this repository to your computer
2. Open TeXStudio
3. Go to **File** → **Open**
4. Navigate to the repository folder
5. Select **`template.tex`** and click **Open**

#### Step 5: Compile the Resume

1. Press **F5** (or click **Tools** → **Build & View**)
2. If prompted to install missing packages, click **Install**
3. Wait for compilation to complete
4. The PDF will appear in the preview pane

---

### Option 2: Overleaf (Online)

This is the easiest option - no installation required!

#### Step 1: Create an Overleaf Account

1. Go to [https://www.overleaf.com](https://www.overleaf.com)
2. Sign up for a free account

#### Step 2: Create a New Project

1. Click **New Project** → **Upload Project**
2. Upload a ZIP file containing all files from this repository:
   - `template.tex`
   - `twentysecondcv.cls`
   - `300x300.jpg` (your profile picture)
3. Click **Upload**

#### Step 3: Compile the Resume

1. Open the project
2. Click the **Recompile** button (or press **Ctrl+Enter**)
3. The PDF will appear in the preview pane
4. Download by clicking **Download PDF**

**Note**: If you encounter timeout issues on Overleaf, try:
- Splitting compilations (click "Recompile from scratch")
- Using a simpler profile picture (smaller file size)

---

### Option 3: TeX Live (Linux/macOS)

#### Linux (Ubuntu/Debian)

```bash
# Install TeX Live
sudo apt-get update
sudo apt-get install texlive-latex-base texlive-fonts-recommended texlive-fonts-extra texlive-latex-extra

# Compile the resume
cd /path/to/repository
pdflatex template.tex
pdflatex template.tex  # Run twice for cross-references
```

#### macOS

1. Download MacTeX from [https://www.tug.org/mactex/](https://www.tug.org/mactex/)
2. Install the package
3. Open Terminal and navigate to the repository:

```bash
cd /path/to/repository
pdflatex template.tex
pdflatex template.tex  # Run twice for cross-references
```

---

## Compiling the Resume

### Using TeXStudio
- Press **F5** to compile and view
- Press **F6** to compile only
- Press **F7** to view the PDF

### Using Command Line
```bash
# Navigate to the project folder
cd /path/to/personal_resume

# Compile (run twice for cross-references)
pdflatex template.tex
pdflatex template.tex

# Output: template.pdf
```

---

## Customizing Your Resume

### Personal Information

Edit these commands in `template.tex` after `\begin{document}`:

```latex
\profilepic{300x300.jpg}           % Your profile picture (replace file)
\cvname{Your Name}                  % Your full name
\cvjobtitle{Your Job Title}         % Your job title (optional, leave {} empty)
\cvdate{Your Date of Birth}         % Date of birth
\cvaddress{Your Address}            % Full address
\cvnumberphone{+1 234 567 8900}     % Phone number
\cvmail{your.email@example.com}     % Email address
\cvsite{github.com/yourusername}    % Website/GitHub (use \href{}{} for links)
\cvlinkedin{linkedin.com/in/you}    % LinkedIn (optional, leave {} empty)
```

### Profile Picture

- Replace `300x300.jpg` with your own photo
- Recommended size: 300x300 pixels (square)
- Supported formats: JPG, PNG

### Sections

The template includes these sections:
- **About Me** (`\aboutme{}`)
- **Technical Skills** (`\technicalskill{}`)
- **Soft Skills** (`\softskillset{}`)
- **Languages** (`\languages{}`)
- **Work Experience** (use `\begin{twenty}...\end{twenty}`)
- **Achievements** (use `\begin{twenty}...\end{twenty}`)
- **Certifications** (use `\begin{twentyshort}...\end{twentyshort}`)
- **Education** (use `\begin{twenty}...\end{twenty}`)

### Adding Entries

#### For entries with descriptions (Work Experience, Education):
```latex
\begin{twenty}
    \twentyitem{Dates}{Title}{Location/GPA}{Description}
\end{twenty}
```

#### For short entries (Certifications, Awards):
```latex
\begin{twentyshort}
    \twentyitemshort{Date}{Title}
\end{twentyshort}
```

---

## Troubleshooting

### Common Errors and Solutions

| Error | Solution |
|-------|----------|
| `Undefined control sequence \cvjobtitle` | Add `\cvjobtitle{}` in your template.tex |
| `Undefined control sequence \cvlinkedin` | Add `\cvlinkedin{}` in your template.tex |
| `File not found: 300x300.jpg` | Ensure your profile picture is in the same folder |
| `Missing package` | Let MiKTeX auto-install, or run `tlmgr install <package>` |
| `Font shape undefined` | This is a warning, not an error - the PDF will still compile |

### Overleaf Timeout Issues

If Overleaf times out during compilation:
1. Click **Menu** → **Recompile from scratch**
2. Use a smaller profile picture (reduce file size)
3. Remove unused packages or sections
4. Consider using MiKTeX locally instead

### Package Installation (MiKTeX)

If MiKTeX doesn't auto-install packages:
1. Open **MiKTeX Console** (search in Start menu)
2. Go to **Packages**
3. Search for the missing package
4. Right-click and select **Install**

---

## File Structure

```
personal_resume/
├── template.tex          # Main resume file - EDIT THIS
├── twentysecondcv.cls    # Template class file - DON'T EDIT
├── 300x300.jpg           # Profile picture
├── README.md             # This file
└── LICENSE               # MIT License
```

---

## License

This template is based on the **Twenty Seconds CV** template by Carmine Spagnuolo with modifications by Vel (LaTeXTemplates.com).

Released under the MIT License. See [LICENSE](LICENSE) for details.