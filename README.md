# Nextcloud Photo Fixer

A  script to correct file modification dates in Nextcloud based on EXIF metadata or supplemental JSON metadata files (e.g., Google Takeout). It ensures that photos and videos display the correct date in the Nextcloud Photos app.

## Features
- Applies EXIF `DateTimeOriginal` to file modification dates.
- Extracts creation time from supplemental JSON metadata files (`*.json` and `*.supplemental-m.json`).
- Supports `.jpg`, `.jpeg`, `.mp4` and other common formats.
- Avoids re-processing files that already have the correct date.
- Efficient and clean logging.

## Installation
1. Clone the repository:

```bash
git clone https://github.com/yourusername/nextcloud-photo-fixer.git
cd nextcloud-photo-fixer
```

2. Make the script executable:

```bash
chmod +x fix_photo_dates.sh
```

3. Install dependencies:

```bash
sudo apt update
sudo apt install jq libimage-exiftool-perl -y
```

## Usage

Run the script for a specific folder:

```bash
sudo ./fix_photo_dates.sh "/path/to/nextcloud/data/username/files/Photos from 2014"
```

Or, run for the entire `files` directory:

```bash
sudo ./fix_photo_dates.sh
```

### Example with JSON Metadata Files
If you have `.json` or `.supplemental-m.json` files with creation timestamps, the script will extract the `photoTakenTime` value and apply it as the file modification date.

## 🛠Configuration
- Modify the `DEFAULT_DIR` variable in the script to set a default path.
- Log file location: `/var/log/nextcloud_photo_fix.log`

## License
MIT License.
