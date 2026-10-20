# Xiaomi Everpal (MT6833) HyperOS 4 / Android 17 Vendor Tree

Unified vendor repository tailored to boot **Xiaomi HyperOS 4 (Android 17)** and HyperOS 1/2/3 ports & GSIs on **Xiaomi Everpal** (MediaTek Dimensity 700 / MT6833 platform).

## Supported Devices
- Redmi Note 11 5G (China) / `evergo`
- Redmi Note 11T 5G (India) / `evergo`
- POCO M4 Pro 5G / `evergreen`
- Redmi Note 11S 5G / `opal`

## Features & Improvements
- **Xiaomi HyperOS Proprietary Services**:
  - `vendor.xiaomi.hardware.displayfeature@1.0`: Support for Vivid, Saturated, Paper mode, and DC dimming.
  - `vendor.xiaomi.hardware.touchfeature`: Low-latency gaming touch responsiveness, palm rejection on `/dev/xiaomi-touch`.
  - `vendor.xiaomi.hardware.citsensorservice@1.1`: Hardware sensor diagnostics & calibration.
  - `vendor.xiaomi.hardware.fingerprintextension@1.0`: Fingerprint gestures and screen-off unlock integration.
  - `vendor.xiaomi.hardware.motor@1.0`: Framework compatibility service.
- **Audio & SoundFX**:
  - Full MT6833 audio calibration with Aurisys parameters.
  - Xiaomi Mi Sound FX & Spatial Audio pipeline definition in `audio_effects_hyperos.xml`.
- **Thermal & Performance**:
  - Tuned `thermal_hyperos.conf` for Dimensity 700 octa-core CPU & Mali-G57 GPU balancing.
  - Android 17 memory management & ZRAM LZ4 compression governor.
- **VINTF & SELinux**:
  - Target-level VINTF compatibility matrix declaring all Xiaomi HALs to prevent boot-time framework panics.
  - Complete vendor SELinux policy contexts (`hwservice_contexts`, `service_contexts`, `file_contexts`).

## How to Build / Integrate
1. Place this tree in `vendor/xiaomi/everpal` within your Android 17 / lineage-24.0 build environment.
2. Ensure device tree is configured in `device/xiaomi/everpal`.
3. Include `vendor/xiaomi/everpal/everpal-vendor.mk` from `device.mk`.
4. Compile vendor target:
   ```bash
   m vendorimage
   ```
