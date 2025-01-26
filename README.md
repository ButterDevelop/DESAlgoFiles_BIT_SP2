# DESAlgoFiles_BIT_SP2

## Overview

**DESAlgoFiles_BIT_SP2** is a Python-based application designed to encrypt and decrypt files using the Data Encryption Standard (DES) algorithm. This project successfully fulfills the requirements of **Úkol 2 - DES**, providing a robust solution for handling file encryption and decryption with proper padding and key management.

## Features

- **DES Encryption & Decryption**: Implements the DES algorithm in Electronic Code Book (ECB) mode to securely encrypt and decrypt files.
- **File Handling**: Processes files as byte arrays, ensuring compatibility with various file types.
- **Padding Management**: Utilizes zero padding to handle files whose sizes are not multiples of 64 bits, ensuring data integrity during encryption and decryption.
- **Key Generation**: Generates a pseudo-random 64-bit DES key, stored in `key.txt` in hexadecimal format.
- **Progress Tracking**: Provides real-time updates on the number of processed blocks, enhancing user awareness during long operations.
- **Command-Line Interface**: Supports simple command-line arguments for encryption (`-e`) and decryption (`-d`).

## How It Works

1. **Key Generation**: Upon first run, the program generates a 64-bit DES key and saves it as `key.txt` in hexadecimal format.
2. **Encryption (`-e`)**:
   - Reads all files from the `validation/` directory.
   - Applies zero padding to ensure each file's size is a multiple of 64 bits.
   - Encrypts each file block-by-block using DES in ECB mode.
   - Saves the encrypted files in the `out/` directory with the `.des` extension.
3. **Decryption (`-d`)**:
   - Reads the DES key from `key.txt`.
   - Processes all `.des` files in the `out/` directory.
   - Decrypts each file block-by-block.
   - Removes the padding and restores the original file in the `decoded/` directory.
4. **Validation**: Ensures that decrypted files in `decoded/` match the original files in `validation/`, verifying the correctness of the encryption and decryption processes.

## Usage

Run the program via the command line with the following arguments:

- **Encrypt Files**:
  
  ```bash
  python main.py -e
  ```
  This command will encrypt all files in the validation/ directory and store the encrypted versions in the out/ directory.
- **Decrypt Files**:
  ```bash
  python main.py -d
  ```
  This command will decrypt all .des files in the out/ directory and store the decrypted files in the decoded/ directory.

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute this software as per the license terms.

## Contact

For any questions or feedback, please reach out to me on GitHub.
