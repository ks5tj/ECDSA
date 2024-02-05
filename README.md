# ECDSA Implementation

## Overview

This project implements the Elliptic Curve Digital Signature Algorithm (ECDSA) using Python. It focuses on utilizing small numerical values (all numbers are 1,000 or less) to demonstrate the core principles of ECDSA, including elliptic curve operations, finite field arithmetic, and the ECDSA process itself. This implementation ensures efficiency, with a requirement that operations complete in a reasonable timeframe (approximately a second or less), and emphasizes the importance of logarithmic-time elliptic curve multiplication.

## Prerequisites

- Python 3.x
- No external libraries for field arithmetic or elliptic curve arithmetic are used. Standard libraries are sufficient for this implementation.

## Setup

1. **Clone the repository:**
git clone <repository_url>
3. **Navigate to the project directory:**
cd ecdsa-implementation

## Usage

The project is designed to be executed via a shell script `ecdsa.sh` which forwards commands to the Python script `ecdsa.py`. Ensure you have execution permissions for the script:

chmod +x ecdsa.sh

### Commands

- **Generate User ID:**
./ecdsa.sh userid
- **Generate Key Pair:**
./ecdsa.sh genkey 43 31 25 25
Outputs the private key (`d`), and the public key coordinates (`Qx`, `Qy`).

- **Sign a Message:**
- ./ecdsa.sh sign 43 31 25 25 <private_key> <hash_of_message>
Outputs the signature components (`r`, `s`).

- **Verify a Signature:**
- ./ecdsa.sh verify 43 31 25 25 <public_key_x> <public_key_y> <r> <s> 
- <hash_of_message>
Outputs `True` if the signature is valid, otherwise `False`.

### Testing

The project includes tests to verify each part of the ECDSA process. It's crucial to test each component thoroughly to ensure correctness. Online calculators for elliptic curve operations and finite field arithmetic can be used for verification.

## Key Components

- **Finite Fields:** Implementation includes addition, subtraction, multiplication, division, and exponentiation within finite fields.
- **Elliptic Curve Operations:** Includes point addition, point doubling, and scalar multiplication on the elliptic curve.
- **ECDSA Process:** Covers key generation, message signing, and signature verification.

## Changelog

- Initial version: Implements basic ECDSA functionality with finite field and elliptic curve operations.

## Contributions

Contributions are welcome. Please open an issue or pull request if you have suggestions for improvement.


