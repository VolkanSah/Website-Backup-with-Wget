# Website backup with wget (Update 2023)
This repository contains a minimal script to create a local backup of a website using wget with the options -mkEpnp.

# Usage
### To create a local backup of a website, use the following command:
wget -mkEpnp https://example.com
### This will download the entire website and create a local copy with the same structure as the original website. The options used are:

- -m: Enables mirroring mode, which means the entire website will be recursively downloaded.
- -k: Converts all the links in the downloaded files to local links, so that the website can be browsed offline.
- -E: Adds the .html extension to the downloaded files.
- -p: Downloads all necessary files for each page, such as images and stylesheets.
- -n: Disables file timestamping, so that the local files have the same timestamp as the original files.

## Additional Information
Wget is a command-line utility for downloading files from the web. It supports a wide range of protocols, including HTTP, HTTPS, FTP, and SFTP. With its various options, it can be used for a variety of tasks, such as mirroring websites, downloading large files, and recursive downloads.

## Some other useful options for wget include:

- -c: Continues a previous download that was interrupted or stopped.
- -r: Recursively downloads files from a website, following links and directory structure.
- -nc: Skips downloading files that already exist in the local directory.
- -np: Does not follow links to parent directories.
For more information on wget, consult the official documentation.

## License
This project is licensed under the MIT License 
