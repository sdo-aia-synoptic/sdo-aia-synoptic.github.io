# SDO/AIA Carrington Synoptic Map Archive

**Multiwavelength Solar Synoptic Maps: Construction, Uncertainty Characterization, and Scientific Data Products**

[**Project Website**](https://sdo-aia-synoptic.github.io/) | [**GitHub Organization**](https://github.com/sdo-aia-synoptic)

## 1. Overview

The SDO/AIA Carrington Synoptic Map Archive is a multiwavelength scientific data product developed from observations acquired by the Atmospheric Imaging Assembly (AIA) aboard NASA's Solar Dynamics Observatory (SDO).

The project provides Carrington-coordinate synoptic maps designed to facilitate long-term investigations of the solar atmosphere, solar-cycle variability, coronal structures, and multiwavelength solar activity.

The archive incorporates documented processing procedures, uncertainty characterization, quality-assessment products, and observational provenance to support reproducible scientific analysis.

## 2. Dataset Summary

| Parameter | Description |
|---|---|
| Observatory | Solar Dynamics Observatory (SDO) |
| Instrument | Atmospheric Imaging Assembly (AIA) |
| EUV passbands | 94, 131, 171, 193, 211, 304, 335 Å |
| UV passbands | 1600, 1700 Å |
| Carrington rotations | CR2097–CR2312 |
| Rotations per wavelength | 216 |
| Total baseline wavelength–rotation maps | 1,944 |
| Map dimensions | 1440 × 2891 pixels |
| Temporal sampling | Nominal 6-hour cadence |
| Coordinate representations | CAR and CEA |
| Scientific data format | FITS |
| Visualization format | PNG |
| Data release | In preparation |

The 1,944 baseline maps comprise 1,512 EUV and 432 UV wavelength–rotation products. CAR and CEA are alternative representations of the underlying maps, not independent observations.

Additional uncertainty, quality-control, and UV center-to-limb-variation products are provided separately.

## 3. Synoptic Map Construction

The archive is constructed from AIA Level 1 full-disk observations.

The EUV processing includes pointing correction, image registration, time-dependent degradation correction, and exposure normalization.

The UV processing includes pointing correction, registration, and exposure normalization. Time-dependent degradation correction is not currently applied to the UV branch.

Observations are selected around nominal sampling times using quality-control criteria and observation-time proximity.

Individual images contribute longitudinal strips that are combined using Carrington-coordinate weighting, including periodic treatment of the 0°/360° longitude boundary.

The resulting synoptic maps are distributed in two representations:

- **CAR (Plate Carrée):** Linear heliographic latitude representation.
- **CEA (Cylindrical Equal Area):** Equal-area representation using a sine-latitude grid.

Both representations retain the native output dimensions of 1440 × 2891 pixels.

## 4. Scientific Data Products

### 4.1 Intensity Maps

Exposure-normalized synoptic intensity maps are provided in FITS format.

The baseline EUV and UV intensity products are expressed in DN s⁻¹.

### 4.2 Uncertainty Characterization

The EUV archive provides several internal uncertainty and variability products:

- **Measurement uncertainty:** Estimated from the contributing observations and propagated through the weighted combination.
- **Synoptic dispersion:** Describes the weighted variation among distinct observations contributing to a map pixel.
- **Combined internal uncertainty:** Quadrature combination of the measurement and synoptic terms, intended for uncertainty-aware analysis and DEM weighting.

These products do not represent a complete physical error budget. In particular, they do not fully account for instrumental response uncertainties, atomic physics, absolute calibration systematics, or all spatial and temporal correlations.

### 4.3 Quality-Control Products

Quality and observational-support diagnostics include:

- Accumulated contribution weights
- Number of contributing observations
- Effective sample count
- Weighted temporal-offset diagnostics
- Valid-pixel coverage information
- Processing and observational metadata

### 4.4 UV Center-to-Limb Products

For the 1600 and 1700 Å channels, separately labeled center-to-limb-variation-relative (CLV-relative) maps are included.

These products are dimensionless and must be distinguished from the baseline UV maps in DN s⁻¹.

## 5. Data Coverage and Validation

The archive covers 216 consecutive Carrington rotations for each of the nine wavelength channels.

Across the 1,512 EUV baseline maps, the median valid-pixel coverage is approximately 99.8%.

Some rotations contain substantially reduced observational coverage. Such regions are retained as missing data rather than being artificially reconstructed.

External morphological validation has been performed against the NASA/SSC SDO/AIA Carrington-map product for the four common wavelengths: 171, 193, 211, and 304 Å.

These comparisons assess spatial agreement and do not constitute independent absolute radiometric calibration.

A separate six-channel coronal Differential Emission Measure (DEM) demonstration illustrates the usability of the intensity and internal uncertainty products for downstream scientific analysis. It does not independently validate the DEM inversion method or AIA temperature-response functions.

## 6. Data Formats and Access

The scientific archive is organized around individual wavelength channels and Carrington rotations.

**FITS files** contain the quantitative scientific products and associated metadata.

**PNG files** are provided as quicklook visualizations for inspection and quality assessment. They should not be used for quantitative measurements.

**Metadata and catalog files** are intended to document processing parameters, observational provenance, file availability, and data integrity.

The planned public archive will provide individual FITS and PNG files without requiring users to download the complete collection.

The authoritative data repository and persistent dataset identifiers will be announced following release preparation and repository validation.

## 7. Interactive Map Explorer

The project website is:

https://sdo-aia-synoptic.github.io/

The map explorer is being developed to support:

- Selection of AIA wavelength
- Selection of Carrington rotation
- Selection of CAR or CEA projection
- Selection of scientific product
- Visualization of PNG quicklooks
- Links to corresponding FITS files
- Access to dataset documentation and citation information

The full interactive browsing functionality and public data endpoints are under development.

## 8. Software and Reproducibility

The processing and analysis workflows use Python and MATLAB, together with relevant solar-physics and scientific-computing packages.

Software dependencies include components of SunPy, Astropy, aiapy, NumPy, SciPy, and associated analysis tools.

Processing software, configuration information, quality-control methods, and reproducibility documentation are being prepared for public release.

## 9. Citation and Acknowledgments

A companion scientific manuscript describing the construction, uncertainty characterization, and validation of the archive is in preparation.

A recommended dataset citation and persistent DOI will be provided following publication of the public archive.

The archive is derived from observations acquired by the Atmospheric Imaging Assembly aboard NASA's Solar Dynamics Observatory.

Official mission information:

- [NASA Solar Dynamics Observatory](https://sdo.gsfc.nasa.gov/)
- [SDO/AIA Instrument](https://aia.lmsal.com/)
- [Joint Science Operations Center (JSOC)](http://jsoc.stanford.edu/)

## 10. Project Status

**Current status:** Archive documentation and public distribution infrastructure are under development.

This GitHub repository hosts the project website. Scientific data, source code, and detailed documentation will be linked through the project organization as their public releases are finalized.

Licensing information and release-specific citation instructions will be added before the corresponding public distributions.

---

**SDO/AIA Carrington Synoptic Map Archive**

*An independent scientific data-product project based on NASA SDO/AIA observations. This repository and website are not official NASA services.*
