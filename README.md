# 3D-Printed DIY Visible Spectrophotometer

This repository accompanies the manuscript *Performance and Limitations of a 3D-Printed, Camera-Based DIY Spectrophotometer for Analytical Chemistry Education*. It contains the experimental images, commercial UV–Vis reference data, analysis code, 3D-printable files, and an illustrated assembly guide for a camera-based spectrophotometer adapted from an open-source NanoDrop-style design.

## Build the spectrophotometer

Open the [`DIY_Spectrophotometer_Assembly_Guide.pdf`](DIY_Spectrophotometer_Assembly_Guide.pdf) for a visual inventory of the printed parts, enclosure assembly instructions, and a diagram of the optical path. The guide explains how to align the mirror with the USB webcam fixed in place and how to check for a spectral band in Theremino Spectrometer. For mirror placement and alignment, see **04 / Optical Placement** on page 5 of the guide. The PDF is at the repository root, separate from the 3D files archive.

## Run the analysis in Google Colab

1. Download [`CodeSpectra_ENGLISH.ipynb`](CodeSpectra_ENGLISH.ipynb) and [`Code Data_CSV and Images.zip`](Code%20Data_CSV%20and%20Images.zip) from this repository.
2. On your computer, extract **only the outer archive**, `Code Data_CSV and Images.zip`. Open the extracted `Code Data - Copy` folder. Keep the inner archive, `DIY Spectrophotometer Code Images.zip`, zipped.
3. Open [Google Colab](https://colab.research.google.com/), upload `CodeSpectra_ENGLISH.ipynb`, and select **Runtime → Run all**.
4. When the notebook prompts you for data, select the following **nine files together** from `Code Data - Copy`:

   | Files to upload | Contents |
   | --- | --- |
   | `DIY Spectrophotometer Code Images.zip` | Original spectral photographs, including wavelength references, the dark frame, blanks, and samples |
   | All seven `Barrido*.csv` files | Commercial UV–Vis spectra and reference measurements |
   | `Curva Referencia.xlsx` | Reference workbook for the concentration series |

   **Do not upload only the outer archive.** The notebook does not extract ZIP archives nested inside other ZIP archives. Uploading only the outer archive leaves the required photographs unavailable to the analysis.

5. Let the remaining cells run. At the end, Colab downloads `DIY Visible Spectra_Complete_Results.zip`, which contains selected figures, numerical results, and an output manifest. If the browser blocks the download, find the archive in Colab’s **Files** panel and download it from there.

## Adapt the code to your own setup
First, run the notebook with the included dataset to check that the workflow runs as expected. For a different instrument, capture your own wavelength reference images, dark frame, blanks, and sample images. Then update the input filenames and reference wavelengths in the notebook’s configuration section.

By default, the code averages the 11 central rows of each image. If the spectrum is not centered in your images, adjust the rows used for extraction.

## Repository contents

The guide, code, and ZIP archives are at the repository root. The nested folder below appears only after extracting the outer data ZIP.

- **GitHub repository root**
  - 📄 [`DIY_Spectrophotometer_Assembly_Guide.pdf`](DIY_Spectrophotometer_Assembly_Guide.pdf) ← **Start here to build the instrument.** See page 5 for optical placement and alignment.
  - 📦 [`Nanodrop-Style Visible Spectrophotometer 3D Files.zip`](Nanodrop-Style%20Visible%20Spectrophotometer%203D%20Files.zip) — 3D design files and original license notices.
  - 📦 [`Theremino Spectrometer.zip`](Theremino%20Spectrometer.zip) — spectral image acquisition software.
  - 📄 [`CodeSpectra_ENGLISH.ipynb`](CodeSpectra_ENGLISH.ipynb) — executable Google Colab notebook.
  - 📄 [`CodeSpectra_ENGLISH.py`](CodeSpectra_ENGLISH.py) — Python export of the notebook.
  - 📦 [`Code Data_CSV and Images.zip`](Code%20Data_CSV%20and%20Images.zip) — input archive for the analysis.
    - 📁 `Code Data - Copy/` — folder inside the extracted archive.
      - 📦 `DIY Spectrophotometer Code Images.zip` — keep this inner archive zipped for Colab.
      - 📄 Seven `Barrido*.csv` files and `Curva Referencia.xlsx` — upload all eight files with the inner image ZIP.

## What the results mean

The notebook averages the **11 central rows** of each spectral image. For the dataset provided here, the code uses reference wavelengths of **365, 405, 532, and 650 nm** to map pixels to wavelengths. These values are settings for this experiment, not specifications for the prototype. If you build a different setup or use other reference sources, update the calibration settings and use calibration images from your own setup. The commercial reference spectra included in this repository cover **300–700 nm**. 

The DIY absorbance values are **apparent absorbance** estimates derived from dark-corrected JPEG intensities. They are useful for exploring how illumination, weak signals, and possible sensor saturation affect a measurement. The prototype is an educational tool for studying spectral acquisition and instrument limitations, not a validated method for quantifying concentrations or reliably identifying absorption maxima.

## Licenses and third-party materials

### Analysis code

The analysis script [`CodeSpectra_ENGLISH.py`](CodeSpectra_ENGLISH.py) and the Colab notebook [`CodeSpectra_ENGLISH.ipynb`](CodeSpectra_ENGLISH.ipynb) are made available under [CC0 1.0 Universal](LICENSE-CODE).

### Experimental data and documentation

The experimental data, spectral photographs, and original content in the assembly guide produced for this study are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). This license does not cover third-party material.

### 3D Design Attribution and License

The experimental prototype was adapted from the [Nanodrop-Style UV-Vis Spectrophotometer by KysonMuh on Thingiverse](https://www.thingiverse.com/thing:6723282). The 3D files retain their original Creative Commons Attribution–ShareAlike (CC BY-SA) license and attribution notices, as provided in the 3D files archive.

### Theremino Spectrometer

Theremino Spectrometer was used to acquire spectral images. It is third-party software and is not covered by this repository's CC0 1.0 Universal dedication or CC BY 4.0 license. The software and manuals are available from the [official Theremino Spectrometer download page (https://www.theremino.com/downloads/automation#spectrometer).

<sub><strong>AI assistance.</strong> ChatGPT (OpenAI, GPT-6) assisted with drafting and editing this README. ChatGPT (OpenAI) was also used to generate, debug, and optimize the Python analysis code. The authors developed the analysis workflow iteratively, reviewed the documentation, and tested the code.</sub>
