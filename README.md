# Solana Hello world
This is a minimal "Hello, Solana!" smart contract written in Rust, deployed and tested on a local Solana test validator.
---

## Solana Installation

On Mac, run this single command to install all dependencies.

```curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash```
<img width="486" alt="Screenshot 2025-04-14 at 3 22 52 PM" src="https://github.com/user-attachments/assets/f3b15357-6bbc-48ff-b089-15c23129d980" />

## Wallet address

<img width="491" alt="Screenshot 2025-04-14 at 3 27 19 PM" src="https://github.com/user-attachments/assets/25335fa5-4c69-4aff-85cd-e2daeffdbaab" />


## 🚀 Running Locally

### 1. Start Solana Test Validator

```solana-test-validator```

<img width="952" alt="Screenshot 2025-04-15 at 7 33 52 PM" src="https://github.com/user-attachments/assets/aefbaa0a-7a5d-4782-8162-267891df51bd" />


### 2. Build the Program
```cargo build-bpf```
This compiles your program to BPF format for deployment.

### 3. Deploy the Program
After building, deploy the smart contract to the local validator:

```solana program deploy ./target/deploy/hello_world.so```
This command will return a Program ID. Copy it.

<img width="935" alt="Screenshot 2025-04-15 at 7 40 25 PM" src="https://github.com/user-attachments/assets/fed846e4-dac3-4240-8c4e-836a6d2ee395" />

### 4. Update Program ID in Client
Open your client.rs or main.rs file and replace the line with the actual deployed Program ID:

```let program_id = Pubkey::from_str("PASTE_YOUR_PROGRAM_ID_HERE").unwrap();```


### 5. Run the Off-Chain Client
Send a transaction to your deployed smart contract using the client code:

```cargo run --example client```

<img width="790" alt="Screenshot 2025-04-15 at 7 41 39 PM" src="https://github.com/user-attachments/assets/a60417a5-a3c4-44fb-bcd9-f345fae05d2b" />
<img width="789" alt="Screenshot 2025-04-15 at 7 42 04 PM" src="https://github.com/user-attachments/assets/190bc1b0-6699-4374-9ad3-3310ddb55663" />


You should see a transaction signature printed and "Hello, Solana!" in the validator logs.
