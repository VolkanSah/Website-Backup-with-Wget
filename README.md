
# Website Backup with wget (Update 2024)

This repository contains a comprehensive guide and script to create a local backup of a website using `wget` with various options to optimize the download process.

## Usage

### Basic Command

To create a local backup of a website, use the following command:
```sh
wget -mkEpnp https://example.com
```
This will download the entire website and create a local copy with the same structure as the original website. The options used are:

- `-m`: Enables mirroring mode, which means the entire website will be recursively downloaded.
- `-k`: Converts all the links in the downloaded files to local links, so that the website can be browsed offline.
- `-E`: Adds the .html extension to the downloaded files.
- `-p`: Downloads all necessary files for each page, such as images and stylesheets.
- `-np`: Does not follow links to parent directories.

### Additional Useful Options

- `-c`: Continues a previous download that was interrupted or stopped.
- `-r`: Recursively downloads files from a website, following links and directory structure.
- `-nc`: Skips downloading files that already exist in the local directory.
- `--timeout=SECONDS`: Sets the read timeout for downloads. This can be useful if you want to stop the download after a certain period of inactivity and retry later.
- `--limit-rate=RATE`: Limits the download speed to avoid saturating your network.
- `--tries=NUMBER`: Sets the number of retries for downloading files.

### Examples

#### Setting a Timeout and Retrying Later
```sh
wget -mkEpnp --timeout=30 -c https://example.com
```
This command sets a timeout of 30 seconds. If the download is interrupted due to the timeout, it can be resumed with the `-c` option.

#### Limiting the Download Speed
```sh
wget -mkEpnp --limit-rate=100k https://example.com
```
This command limits the download speed to 100 KB/s to prevent network congestion.

#### Increasing the Number of Retries
```sh
wget -mkEpnp --tries=20 -c https://example.com
```
This command increases the number of retries to 20, which is useful for unstable connections.

#### Creating a Log File
```sh
wget -mkEpnp -c -o download.log https://example.com
```
This command creates a log file named `download.log` to monitor the download progress and debug any issues.

### Parallelized Downloads with aria2
If the website loads resources from multiple domains, consider using `aria2` for parallel downloads:
```sh
aria2c -x 16 -k 1M https://example.com
```
This command uses `aria2` to make up to 16 parallel connections with a segment size of 1 MB.

## Additional Information

`wget` is a command-line utility for downloading files from the web. It supports a wide range of protocols, including HTTP, HTTPS, FTP, and SFTP. With its various options, it can be used for a variety of tasks, such as mirroring websites, downloading large files, and recursive downloads.

For more detailed information on `wget`, consult the [official documentation](https://www.gnu.org/software/wget/manual/wget.html).
- [Source of this resposerity](https://github.com/VolkanSah/Website-Backup-with-Wget)

## License

This project is licensed under the MIT License.


