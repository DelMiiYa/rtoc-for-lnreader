# A Regressor's Tale of Cultivation EPUB Generator

A Python script to generate an EPUB of ***A Regressor's Tale of Cultivation*** from [We Tried TLs](https://wetriedtls.com/series/a-regressors-tale-of-cultivation).

## Features
- **LNReader Optimized**: Native integration with [LNReader](https://github.com/LNReader/lnreader) — full support for reader themes (Light, Dark, AMOLED), font size, line height, padding sliders, and the font picker, with inline base64 fonts and a clean spine without ghost chapters.
- **Built for E-Readers**: Generates a clean EPUB with a book cover, Table of Contents, and metadata.
- **Ad-Free Experience**: Automatically removes website clutter, pop-ups, and promotional text.
- **Automatic Updates**: Run it once to get the whole book; run it again later to pick up only the newly released chapters.
- **Smart Formatting**: Correctly handles tricky merged chapters (like 807-808), includes author's notes/Q&As, and adds official cover art.
- **High Performance**: Optimized for speed, limited only by your internet connection.

## Quick Start

### 1. Set up the environment
It is **highly recommended** to use a virtual environment to avoid conflicts (and it's required on many modern systems).

> **Note:** Depending on your system, you may need to use `python3` instead of `python`, and `pip3` instead of `pip` in the steps below.

**Windows (PowerShell):**
```powershell
# Create virtual environment
python -m venv .venv

# Allow script execution (run if activation fails)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# Activate it
.\.venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt
python -m playwright install chromium
```

**Mac/Linux:**
```bash
# Create virtual environment
python -m venv .venv

# Activate it
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
python -m playwright install chromium
```

### 2. Run the generator
```bash
python main.py
```
*Note: Requires an active internet connection. The final EPUB and a cache folder (`data/`) will be generated in the current directory.*

## Advanced Usage
- **Specific Chapters** (by index):
  ```bash
  python main.py 0 1 100 807808
  ```
- **Force Re-generate** (bypass cache):
  ```bash
  python main.py --force
  ```
- **Force specific chapters**:
  ```bash
  python main.py 0 1 --force
  ```

## Which E-Reader to use?
The generated EPUB is standard EPUB 3 and works seamlessly across modern readers:
- **[LNReader](https://github.com/LNReader/lnreader)** (Recommended):
  - **Full UI Customization**: Adjust font size, line-height, horizontal padding, and colors freely without being overridden by EPUB styles.
  - **Dynamic Theme Compatibility**: Adapts cleanly to Default, Dark, AMOLED, and custom themes (`opacity: 0.7` timestamps, responsive text).
  - **Font Picker & Embedded Fonts**: Defaults to `Open Sans` (and `NotoSerifTC` for CJK characters), but cleanly yields when selecting custom fonts in LNReader's settings. Fonts are base64-inlined into `style/nav.css` so they render properly even though LNReader discards the EPUB `fonts/` folder on import.
  - **Clean Spine**: No ghost chapters (no standalone `cover.xhtml` or `nav.xhtml` imported into your chapter list) while maintaining full EPUB 3 manifest compliance.
- **Android**: [Moon+ Reader](http://www.moondownload.com/) (Free), [ReadEra](https://readera.org/), [Librera](https://librera.mobi/), and [Lithium](https://play.google.com/store/apps/details?id=com.faultexception.reader). [Google Play Books](https://play.google.com/store/apps/details?id=com.google.android.apps.books) also works.
- **iOS/Mac**: The built-in **Apple Books** app handles these files perfectly.
- **Kindle**: You can easily import the EPUB file using the [Send to Kindle](https://www.amazon.com/sendtokindle) service.

## Contributing
Issues and feature requests are welcome!
- **Found a bug?** Please report it through [GitHub Issues](https://github.com/vishudhshah/rtoc/issues).
- **Want to contribute?** Submit a Pull Request (PR) with a clear description of your changes. I'll review them as soon as I can.
- **Enjoying the project?** Consider giving it a star!

## Disclaimer
- This tool is intended for personal, offline reading for fans who want a better mobile experience. Please do not use this tool for mass distribution or commercial purposes.
- **Free Chapters Only**: To avoid legal consequences and respect the translators, this script **only generates freely available chapters**. 
- **Adaptability**: While written specifically for *A Regressor's Tale of Cultivation*, the logic can theoretically be adapted for any series on We Tried TLs with some minor adjustments to handle series-specific edge cases.

To respect the hard work of the original author and the translation team at We Tried TLs, **this repository does not host the generated EPUB file.** Consider supporting the original creators!
- **Official Site:** [We Tried TLs](https://wetriedtls.com/series/a-regressors-tale-of-cultivation)
- **Discord:** Join the [We Tried Discord](https://dsc.gg/wetried) for community updates and ko-fi link.
- **Official Author:** Support the author of the webnovel, 엄청난 (Tremendous), on [Munpia](https://novel.munpia.com/346981) or [Naver](https://series.naver.com/novel/detail.series?productNo=9807283).
