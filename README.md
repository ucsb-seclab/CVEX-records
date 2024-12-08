# CVEX-records

What are CVEX-records?

CVEX-records is a collection of executable CVEs that can be run using https://github.com/ucsb-seclab/CVEX.

## Contributions

To contribute a new CVEX record, create a pull request for a new subfolder with the following structure:
```
CVE-XXXX-YYYYY
├── cvex.yml
├── data
│   ├── file1.ext
│   ├── file2.ext
│   ├── file3.ext
│   ├── ...
│   └── fileN.ext
├── ansible_playbook1.yml
├── ansible_playbook2.yml
├── ansible_playbook3.yml
├── ...
└── ansible_playbookN.yml
```

* Briefly describe the vulnerability and the exploit in the first comment of the pull request. Provide clear instructions on how to verify that the exploit succeeded.
* Keep the vulnerable software and the exploit in the `data` folder. Use Git LFS (Large File Storage) for big files. Do not rely on `apt install`, `pip`, URLs or similar methods to download vulnerable software or exploits.
* Build the exploit from the source code. Never commit binaries unless you have a specific reason to do so.
* Rely on built-in Ansible commands. For example, use `ansible.builtin.pip` instead of executing `pip` from shell.
* Consider the logs: for network-based vulnerabilities, ensure that CVEX captures the network interactions in PCAP; for local vulnerabilities, ensure that CVEX captures the API calls of the vulnerable service and/or the exploit.
* **Always test your changes before commiting code.**

