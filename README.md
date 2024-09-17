# File Manager: Automate File Management

This Python script automates the process of organizing files in a specific folder (e.g., your Downloads folder) into subdirectories based on their file extensions. The script monitors the folder for changes and instantly moves files into designated folders (for audio, video, images, and documents) whenever new files are added.

## Features

- **Automatic File Sorting**: Files are moved into respective folders based on their extensions.
  - Audio files (e.g., `.mp3`, `.wav`)
  - Video files (e.g., `.mp4`, `.avi`)
  - Image files (e.g., `.jpg`, `.png`)
  - Document files (e.g., `.pdf`, `.docx`)
- **Duplicate Handling**: If a file with the same name already exists in the destination folder, the script automatically renames the new file to avoid overwriting.
- **Real-Time Monitoring**: The script uses the `watchdog` module to continuously monitor a directory and organize newly added files instantly.
- **Customizable Folders**: You can configure the source folder and destination folders for each file type.

## Prerequisites

Before running the script, ensure you have the following installed:

- Python 3.x
- Required Python modules:
  - `watchdog`
  - `shutil`
  - `os`
  - `time`

You can install the required dependencies using the following command:

```bash
pip install watchdog
```

## Setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-username/file-management-automator.git
   cd file-management-automator
   ```

2. **Configure the script**:
   
   Open the `file_organizer.py` file and specify the folder paths:
   
   - `source_dir`: The directory to monitor (e.g., your Downloads folder).
   - `dest_dir_sfx`: Directory for small sound effects (optional).
   - `dest_dir_music`: Directory for music/audio files.
   - `dest_dir_video`: Directory for video files.
   - `dest_dir_image`: Directory for image files.
   - `dest_dir_documents`: Directory for document files.

   Example:

   ```python
   source_dir = "/Users/username/Downloads"
   dest_dir_music = "/Users/username/Documents/Organized/Music"
   dest_dir_video = "/Users/username/Documents/Organized/Videos"
   dest_dir_image = "/Users/username/Documents/Organized/Images"
   dest_dir_documents = "/Users/username/Documents/Organized/Documents"
   ```

3. **Run the script**:

   Once you've configured the paths, you can run the script:

   ```bash
   python file_organizer.py
   ```

   The script will start monitoring the `source_dir` for changes and move files to the respective folders.

## How It Works

- The script monitors the `source_dir` folder for any new files or changes.
- When a file is added or modified, the script checks its extension and moves it to the appropriate folder.
- If a file with the same name already exists in the destination folder, the script renames the file by appending a counter (e.g., `file(1).jpg`).

## Customization

- **Supported File Types**:
  You can easily customize the supported file types by editing the `image_extensions`, `video_extensions`, `audio_extensions`, and `document_extensions` lists in the script.

  ```python
  image_extensions = [".jpg", ".png", ".gif", ".svg"]
  video_extensions = [".mp4", ".avi", ".mov"]
  audio_extensions = [".mp3", ".wav", ".flac"]
  document_extensions = [".pdf", ".docx", ".pptx"]
  ```

- **Logging**:
  The script logs every action it performs, such as moving files, renaming duplicates, etc. You can check the console for real-time logging or modify the logging configuration to save logs to a file.

