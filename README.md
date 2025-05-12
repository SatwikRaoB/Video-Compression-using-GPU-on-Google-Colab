# 🎥 Video Compression Using GPU on Google Colab

This project demonstrates how to perform **GPU-accelerated video encoding** using **FFmpeg with CUDA/NVENC** inside a **Google Colab** environment. It enables users to compress videos efficiently, inspect media metadata, and even upload video screenshots to ImgBB for sharing or logging.

<br />

---

## 📦 Features

- Mount and unmount **Google Drive** for file access.
- Use **NVIDIA GPU** via CUDA acceleration for fast video processing.
- Convert or re-encode videos using **FFmpeg with NVENC**.
- Extract media metadata with `mediainfo`.
- Choose from multiple audio/video encoding options.
- Automatically upload selected video frames to **ImgBB** for visual confirmation.

<br />

---

## 🧰 Setup Instructions

### 1. Mount Google Drive

- Ensures seamless access to video input/output folders.
- Supports **forced remounting** in case of errors or file updates.


### 2. Pre-Requisites Installation

- Verifies GPU availability using `nvidia-smi`.
- Installs FFmpeg with CUDA support via a GitHub repository.
- Installs `mediainfo` to analyze input/output media files.

<br />

---

## 📁 Input/Output Management

### 3. Inspect Input Video Metadata

- Takes a path to a video file in Drive.
- Uses `mediainfo` to print codecs, resolution, and audio details for verification before processing.


### 4. Full Folder Video Encoding

- Loops through all compatible media files in the input folder.
- Supports several encoding modes:
  - **HEVC with AAC (94k)** bitrate.
  - **HEVC with audio copy or adts-to-asc bitstream filter**.
  - **Copy video stream with new AAC audio**.
- Allows users to set:
  - Output container format (`.mp4`, `.mkv`).
  - Codec profiles (`main`, `main10`).
  - Constant quality values (CQ).
  - Bitrate or CRF control.
- Output is saved to a defined output folder in Drive.

<br />

---

## 🎞️ Post-Processing

### 5. Inspect Encoded Output Metadata

- Same `mediainfo` command as before, applied to output files.
- Confirms successful conversion and codec details.

<br />

---

## 🖼️ Screenshots & Upload (Optional)

### 6. Extract Frames & Upload to ImgBB

- Uses FFmpeg to extract specific time-based frames from the video.
- Each frame is uploaded to **ImgBB** using your personal API key.
- URLs of uploaded images are printed for quick viewing or documentation.

<br />

---

## 💡 Tips

- Ensure your GPU session is active in Colab (`Runtime → Change runtime type → GPU`).
- Input/output folders must exist in Google Drive before encoding begins.
- Use `.mkv` for lossless or `.mp4` for web-friendly output.
- ImgBB usage is optional and API-key driven.

<br />

---

## 📌 Known Issues

- Encoding long videos may result in timeout on free Colab sessions.
- Using special characters or non-English paths in filenames may cause errors.
- Video Copy modes may fail if source codec is unsupported by target format.

<br />

---
