# 🔄 Automatic Backup

A Python-based automatic backup utility that synchronizes files from one or more source folders to a target backup folder.

The program uses **multithreading** to speed up file transfers and automatically **compresses large files using gzip** when they exceed the configured size threshold.

---

## ✨ Features

- 📁 Backup files from one or multiple source folders
- 🔄 Synchronize newer or changed files
- ⚡ Multithreaded file transfer
- 🗜️ Gzip compression for large files
- 💻 Command-line interface
- 📦 Uses only Python standard libraries
- ⚙️ Configurable compression threshold

---

## 🛠️ Technologies Used

- Python 3
- `argparse`
- `gzip`
- `os`
- `shutil`
- `sys`
- `threading`

No external Python packages are required.

---

## 📂 Project Structure

```text
Automatic-Backup/
│
├── Auto_Backup.py
├── README.md
└── .gitignore
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/RaavanHrishi07/Automatic-Backup.git
```

### 2. Navigate to the Project

```bash
cd Automatic-Backup
```

### 3. Check Python Installation

Make sure Python 3 or later is installed:

```bash
python --version
```

---

## ▶️ Usage

The program requires a target backup folder and at least one source folder.

### Basic Usage

```bash
python Auto_Backup.py --target ./Backup_Folder --source ./Source_Folder
```

Short form:

```bash
python Auto_Backup.py -t ./Backup_Folder -s ./Source_Folder
```

---

## 📌 Command-Line Arguments

| Argument | Short Form | Required | Description |
|----------|------------|----------|-------------|
| `--target` | `-t` | Yes | Target backup folder |
| `--source` | `-s` | Yes | Source folder(s) to back up |
| `--compress` | `-c` | No | Gzip compression threshold in bytes |

The default compression threshold is approximately **1024 KB**.

---

## 📁 Multiple Source Folders

The program can accept multiple source folders.

Example:

```bash
python Auto_Backup.py -t ./Backup_Folder -s ./Documents ./Projects ./Images
```

---

## 🗜️ Compression

Files larger than the configured compression threshold are compressed using **gzip** before being stored in the backup location.

For example:

```bash
python Auto_Backup.py -t ./Backup_Folder -s ./Source_Folder -c 100000
```

Here, files larger than `100000` bytes are compressed.

---

## ⚡ Multithreading

The backup process uses Python's `threading` module to transfer files concurrently.

This allows multiple file operations to be processed using separate threads, which can improve backup performance when handling multiple files.

---

## 🔄 How It Works

The backup process follows these basic steps:

1. Read the source and target folders from command-line arguments.
2. Recursively scan the source folders.
3. Check whether a source file is newer than its existing backup.
4. Start a separate thread for files that need to be transferred.
5. Compress files that exceed the configured threshold.
6. Copy smaller files directly using `shutil`.
7. Wait for all backup threads to finish.
8. Display the completion message.

---

## 🖥️ Example Output

```text
------------------------- Start copy -------------------------
______________________________________________________________
Copy ./Source_Folder/example.txt
Compress ./Source_Folder/large_file.dat
______________________________________________________________
------------------------- Done Done! -------------------------
```

---

## 🧪 Testing

The project was tested using a sample source folder containing a test file.

Example:

```text
Test_Source/
└── test.txt
```

The backup was successfully created inside the target backup folder.

---

## 📦 Dependencies

No third-party packages are required.

The project uses only Python's built-in standard library modules.

Therefore, a `requirements.txt` file is not necessary for this project.

---

## 🔐 Notes

- Make sure the target backup location has sufficient storage.
- Use appropriate source and target paths.
- For important data, maintain additional backups rather than relying on a single backup location.
- The compression threshold can be adjusted according to your requirements.

---

## 🔮 Future Improvements

Possible future improvements include:

- Scheduled automatic backups
- Backup logs
- Progress indicators
- Better error reporting
- Configurable backup rules
- Excluding selected file types or folders
- Backup history and versioning
- Optional cloud storage support

---

## 👨‍💻 Author

**Hrishikesh Sharma**

GitHub: [RaavanHrishi07](https://github.com/RaavanHrishi07)

---

## 📄 License

This project is intended for educational and personal use.