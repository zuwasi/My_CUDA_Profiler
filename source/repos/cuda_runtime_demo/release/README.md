# CUDA Profiler GUI - Release Folder

This folder contains build scripts to create distributable versions of the CUDA Profiler GUI.

## Quick Start

### 1. Install Dependencies
```cmd
install_profiler_dependencies.bat
```

### 2. Build Executable

**Option A: Single .exe file (easiest to distribute)**
```cmd
build_profiler_exe.bat
```
Output: `CUDA_Profiler_GUI.exe` (~50-80 MB)

**Option B: Folder with exe + DLLs (faster startup)**
```cmd
build_profiler_folder.bat
```
Output: `CUDA_Profiler_GUI\` folder with executable and libraries

## Distribution

### Single EXE
- Send `CUDA_Profiler_GUI.exe` to users
- Double-click to run
- No Python required

### Folder Distribution
- Zip the `CUDA_Profiler_GUI\` folder
- Extract and run `CUDA_Profiler_GUI.exe`
- Faster startup than single exe

## Requirements on Target Machine

- Windows 10/11
- NVIDIA GPU with CUDA support
- CUDA Toolkit 13.0+
- Nsight Systems 2025.3.2+
- NVIDIA Driver 581.57+

## Files in This Folder

- `install_profiler_dependencies.bat` - Install Python dependencies
- `build_profiler_exe.bat` - Build standalone single .exe
- `build_profiler_folder.bat` - Build folder distribution
- `README.md` - This file

## Source Code

Main application: `..\cuda_profiler_gui.py`

## Troubleshooting

### Build fails with "module not found"
```cmd
pip install --upgrade pyinstaller matplotlib numpy
```

### Executable crashes on startup
- Check CUDA and Nsight Systems are installed
- Run from command prompt to see error messages

### Large file size
- Normal: Single exe is 50-80 MB
- Use folder distribution for smaller individual files

## Version Control

These build scripts are tracked in Git:
```cmd
git add release/*.bat release/README.md
git commit -m "Update release scripts"
git push
```
