# ⚡ WIN11-HARDWARE-OVERRIDE

> **⚠️ DISCLAIMER:** This framework is designed strictly for deploying environments on legacy testing systems. Modifying system verification checks can disrupt built-in OS architecture constraints. Proceed at your own risk.

A collection of lightweight automation tools and registry hooks engineered to inject hardware-compatibility parameters directly into the Windows pre-installation environment (`WinPE`). This override seamlessly nullifies restrictions imposed by **TPM 2.0, Secure Boot, RAM capacity, and unsupported CPUs**.

---

## 🛠️ Framework Core Elements
*   **Zero-Footprint Injection:** Seamlessly edits `HKLM\SYSTEM\Setup\LabConfig` dynamically during runtime.
*   **Live Automation Deployment:** Packaged as both a manual command injection sequence and an automated PowerShell execution string.
*   **Version Neutrality:** Works across modern installation media iterations.

## 🚦 Deployment Matrices

### Vector Alpha: Live System Injections (Manual Setup Mode)
During the initial language-selection phase of the installation environment, execute these triggers to drop into the shell:

1. Hit `SHIFT + F10` to initialize the elevated Command Prompt (`cmd.exe`).
2. Launch the Registry Editor engine:
   ```cmd
   regedit
   ```
3. Navigate into the targeted key array: `HKEY_LOCAL_MACHINE\SYSTEM\Setup`.
4. Provision a secondary key block named `LabConfig` and inject these parameters:
   *   `BypassTPMCheck` (DWORD = 1)
   *   `BypassSecureBootCheck` (DWORD = 1)
   *   `BypassCPUCheck` (DWORD = 1)

---

## 🧪 Quick Run Architecture
To execute the deployment framework strings locally, clone the baseline repository structure:

```bash
git clone https://github.com
cd win11-hardware-override
```
