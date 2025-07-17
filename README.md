# PLX Linux Kernel Driver Suite

A collection of Linux kernel drivers for various PLX PCI/PCIe bridge and DMA controllers, ported and updated to support modern Linux kernels (5.x/6.x+).

---

## Supported Devices

This driver suite includes support for the following PLX chips and modes:

- **PLX 8000 Series**
  - NT-mode driver (Non-Transparent bridging)
  - DMA Controller driver

- **Legacy PLX Bridges**
  - PLX 9050 / 9052 driver
  - PLX 9030 driver
  - PLX 9080 driver
  - PLX 9054 driver
  - PLX 9056 driver
  - PLX 9656 driver

- **PLX 8311 driver**  
  PCIe-to-local bus bridge support

- **PLX 6254 / 6540 / 6466 NT-mode driver**
  Multi-function Non-Transparent bridging

- **PLX PCI / PCIe Service driver**  
  Common utilities and interface layer for PLX-based devices

## Samples

The samples/ directory contains example applications demonstrating usage of the PLX API and driver:
- ApiTest
  - Simple test app that calls various PLX APIs on the selected device and checks return codes.
- DSlave
  - Demonstrates direct read/write to PCI BAR on PLX 9000 devices using the PLX API/driver.
- DSlave_BypassApi
  - Similar to DSlave but maps BAR space into user space directly, bypassing driver for better small-transfer performance.
- LocalToPciInt (9000-series & 8311)
  - Demonstrates waiting for Local-to-PCI interrupts using Notification API.
- NT_DmaTest (8000-series with DMA & NT support)
  - Demonstrates DMA engine usage via NT ports.
- NT_LinkTest (8000-series with NT support)
  - Tests NT link communication by exchanging random-sized data.
- NT_Sample (8000-series with NT support)
  - Sends keyboard input from one system to another via NT port.
- PerfMonitor (8000-series with performance counter support)
  - Uses Performance API to measure and display PLX switch throughput and stats.
- PlxCm
  - Command-line monitor for debugging PLX devices. Full source included.
- PlxDma (9000 & 8000 series)
  - Demonstrates block and SGL DMA transfers.
- PlxDmaPerf (8000-series)
  - Runs continuous block DMA transfers and calculates throughput.
- PlxDmaSglNoApi (9000 & 8000 series)
  - Manually builds SGL descriptors to perform DMA without relying on the PLX API.
- PlxEep
  - CLI tool to read/write EEPROMs attached to PLX devices. Useful in manufacturing.
- PlxNotification
  - Waits for interrupt events using PLX Notification API.
- SampleAppGUI
  - A minimal GUI example that integrates PLX API into a graphical app (e.g., Qt or GTK).
- SerdesEyeTest
  - Example code (not standalone) showing how to access SerDes eye test functionality.
- Shared
  - Utility functions reused across all sample applications for device selection, logging, etc.

