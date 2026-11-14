# 3D-Printed DIY Visible Spectrophotometer

This repository accompanies the manuscript *Performance and Limitations of a 3D-Printed, Camera-Based DIY Spectrophotometer for Analytical Chemistry Education*. It contains the experimental images, commercial UV–Vis reference data, analysis code, 3D-printable files, and an illustrated assembly guide for a camera-based spectrophotometer adapted from an open-source NanoDrop-style design.

## Build the spectrophotometer

Open the [Assembly Guide (PDF)](DIY_Spectrophotometer_Assembly_Guide.pdf) for a visual inventory of the printed parts, enclosure assembly instructions, and a diagram of the optical path. The guide explains how to align the mirror with the USB webcam fixed in place and how to check for a spectral band in Theremino Spectrometer. The PDF can be opened directly in GitHub without downloading the 3D files archive.

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

## Repository contents

| File | Purpose |
| --- | --- |
| [`CodeSpectra_ENGLISH.ipynb`](CodeSpectra_ENGLISH.ipynb) | Executable Google Colab notebook |
| [`CodeSpectra_ENGLISH.py`](CodeSpectra_ENGLISH.py) | Python export of the notebook |
| [`Code Data_CSV and Images.zip`](Code%20Data_CSV%20and%20Images.zip) | Experimental images and commercial reference data |
| [`DIY_Spectrophotometer_Assembly_Guide.pdf`](DIY_Spectrophotometer_Assembly_Guide.pdf) | Illustrated assembly guide and optical alignment check |
| [`Nanodrop-Style Visible Spectrophotometer 3D Files.zip`](Nanodrop-Style%20Visible%20Spectrophotometer%203D%20Files.zip) | 3D design files and original license notices |
| [`Theremino Spectrometer.zip`](Theremino%20Spectrometer.zip) | Image acquisition software archive |

## What the results mean

The notebook averages the **11 central rows** of each spectral image. For the dataset provided here, the code uses reference wavelengths of **365, 405, 532, and 650 nm** to map pixels to wavelengths. These values are settings for this experiment, not specifications for the prototype. If you build a different setup or use other reference sources, update the calibration settings and use calibration images from your own setup. The commercial reference spectra included in this repository cover **300–700 nm**.

The DIY absorbance values are **apparent absorbance** estimates derived from dark-corrected JPEG intensities. They are useful for exploring how illumination, weak signals, and possible sensor saturation affect a measurement. The prototype is an educational tool for studying spectral acquisition and instrument limitations, not a validated method for quantifying concentrations or reliably identifying absorption maxima.

## 3D Design Attribution and License

The experimental prototype was adapted from the [Nanodrop-Style UV-Vis Spectrophotometer by KysonMuh on Thingiverse](https://www.thingiverse.com/thing:6723282). The 3D files archive retains the original attribution and Creative Commons Attribution–ShareAlike (CC BY-SA) license notices.
