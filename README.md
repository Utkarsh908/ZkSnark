# Multiplier Circuit with zk-SNARK Design

This repository contains the code for a multiplier circuit implemented in Circom and its associated zk-SNARK design.

## Overview

The circuit, implemented in Circom, performs the multiplication of two input bits `a` and `b`. Additionally, it demonstrates the use of zero-knowledge succinct non-interactive arguments of knowledge (zk-SNARKs) to prove the correctness of the computation without revealing the inputs or outputs.

## Files

- `multiplier2.circom`: Circom code implementing the multiplier circuit.
- `input.json`: JSON file specifying the input values for the circuit.
- `README.md`: This file, providing an overview of the repository.
- `MultiplierVerifier.sol`: i have used this file for running it

## Usage

1. Install the required dependencies:

  ### Install
`npm i`

### Compile
`npx hardhat circom` 
This will generate the **out** file with circuit intermediaries and geneate the **MultiplierVerifier.sol** contract

### Prove and Deploy
`npx hardhat run scripts/deploy.ts`
This script does 4 things  
1. Deploys the MultiplierVerifier.sol contract
2. Generates a proof from circuit intermediaries with `generateProof()`
3. Generates calldata with `generateCallData()`
4. Calls `verifyProof()` on the verifier contract with calldata

With two commands you can compile a ZKP, generate a proof, deploy a verifier, and verify the proof 
