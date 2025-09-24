# np_calibration_files

**Purpose**
This folder contains probe-specific calibration files for Neuropixels probes used in the lab. These files ensure proper gain and ADC calibration for accurate electrophysiological recordings.



## Folder Structure

- Each subfolder is named after a probe **serial number*- (e.g., `18442114072/`).
- Inside each folder you will find:

  - `<serial>_gainCalValues.csv` — gain calibration values
  - `<serial>_ADCCalibration.csv` — ADC calibration values (only for NP1.0 probes)

Example:

```
np_calibration_files/
└── 18442114072/
    ├── 18442114072_ADCCalibration.csv
    └── 18442114072_gainCalValues.csv
```



## How to Use

Copy the **per-serial folders*- into the directory where your acquisition software expects them:

- **Open Ephys (PXI plugin)**

  - `C:\Users\<username>\AppData\Local\Open Ephys\CalibrationInfo\` (GUI ≥ v1.0.0)
  - `<Open Ephys install folder>\CalibrationInfo\` (any version)
  - `C:\ProgramData\Open Ephys\CalibrationInfo\` (legacy)

- **SpikeGLX**

  - `<SpikeGLX install folder>\Calibration\`

The software will automatically match probes by serial number. No manual editing is required.



## Notes

- **NP1.0*- probes require both gain and ADC calibration files.
- **NP2.0*- probes only use the gain calibration file.
- Keep this repository updated when new probes are added.




