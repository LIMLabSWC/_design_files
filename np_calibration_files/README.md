# np_calibration_files

**Purpose:**
This folder contains calibration and configuration files for Neuropixels probes used in the lab. These files are essential for probe-specific gain and ADC calibration, ensuring accurate electrophysiological recordings.

## Folder Structure & Contents

- Each top-level folder (e.g., `SO1939/`, `2.0/`) corresponds to a batch or version of Neuropixels probes.
- Within each batch/version, subfolders are named by probe serial number (e.g., `19454411222/`).
- Each probe folder contains calibration files:
  - `*_gainCalValues.csv` — Gain calibration values for the probe
  - `*_ADCCalibration.csv` — ADC calibration values
- Additional folders may exist for other probe types or versions.

## File Types & Recommended Software

- `.csv` — Calibration data (open with Excel, LibreOffice, or any text editor)

## How to Use

- **Typical workflow:** Most users simply copy all calibration folders into their OpenEphys or SpikeGLX configuration directory, rather than identifying individual probes. The acquisition software will automatically use the correct calibration file for each probe based on its serial number.
- If needed, you can identify your probe's serial number and locate the corresponding folder.
- Use the calibration files during Neuropixels data acquisition or analysis as required by your workflow.
- For more information on calibration procedures, refer to the main repository README or lab protocols.

## Maintainer

- TBD (add name/email here) 