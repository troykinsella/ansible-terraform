troykinsella.terraform
======================

An ansible role for installing terraform from official archive.

Dependencies
------------

* troykinsella.archive

Role Variables
--------------

* `terraform_version`: Optional. The version of terraform to install. Default: `0.8.4`.
* `terraform_archive_os`: Optional. The target operating system. Default: `linux`.
* `terraform_archive_architecture`: Optional. The target system architecture. Default: `amd64`.
* `terraform_archive_file_name`: Optional. The name of the archive file to download. Default: `terraform_{{terraform_version}}_{{terraform_archive_os}}_{{terraform_archive_architecture}}.zip`.
* `terraform_archive_base_url`: Optional. The installation archive base URL. Default: `https://releases.hashicorp.com/terraform/{{terraform_version}}/`.
* `terraform_archive_checksum`: Optional. The expected installation archive checksum. Default: `297d35d0b4311445cd87ef032d3dec917bcc7a8b163ead28a4c45d966a2f75cc`.
* `terraform_archive_checksum_algorithm`: Optional. The installation archive checksum algorithm. Default: `sha256`.
* `terraform_archive_cache_path`: Optional. The directory path into which the archive will be downloaded. Default: `/usr/local/pkg`.
* `terraform_archive_destination_path`: Optional. The installation prefix directory path. Default: `/usr/local/bin`.
* `terraform_archive_extracted_file_name`: Optional. The expected name of the root file or directory that is extracted from the archive. Default: `terraform`.
* `terraform_archive_destination_file_name`: Optional. Rename the extracted directory to this value.
* `terraform_archive_destination_link_name`: Optional. Create a symbolic link having this name to the `terraform_archive_extracted_file_name` (or `terraform_archive_destination_file_name`, when specified). 

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: troykinsella.terraform
          terraform_version: 0.8.4
          terraform_archive_os: linux
          terraform_archive_architecture: amd64
          terraform_archive_checksum: 297d35d0b4311445cd87ef032d3dec917bcc7a8b163ead28a4c45d966a2f75cc
          terraform_archive_destination_path: /usr/local/bin

License
-------

MIT
