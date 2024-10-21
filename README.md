# namada-setup

## **1. Prerequisites**

Before you start, make sure you have:

- A computer with macOS, Linux, or Windows.
- Ledger hardware wallet (Ledger Nano S or Ledger Nano X).
- Installed Namada binary (`namadad` and `namada-cli`).
- Ledger Live application installed and updated.
- USB cable for connecting Ledger to your computer.

## **2. Install Ledger Namada Application**

### Step 1: Install Ledger Live

If you haven't installed it yet, download and install [Ledger Live](https://www.ledger.com/ledger-live) for your operating system.

1. Open Ledger Live.
2. Connect your Ledger device to your computer via USB.
3. Make sure the Ledger firmware is updated to the latest version.

### Step 2: Install Namada Ledger App

1. Open the **Manager** tab in Ledger Live.
2. Search for "Namada" in the app catalog.
3. Install the **Namada** app on your Ledger device.

After installation, you should see the Namada app on your Ledger device.

## **3. Connecting Ledger to Namada**

Namada uses a command-line interface (CLI) to interact with the blockchain, and it can be integrated with the Ledger for signing transactions securely.

### Step 1: Install Namada CLI

Make sure that `namadad` and `namada-cli` are installed and in your `$PATH`. If you haven't installed them yet, follow these instructions:

1. Download the latest release binaries from [Namada GitHub releases](https://github.com/anoma/namada).
2. Move the binaries to a directory in your system’s PATH, for example:

```bash
sudo mv namada-cli /usr/local/bin/
sudo mv namadad /usr/local/bin/
```

### Step 2: Connect Ledger to Namada

Once your Ledger is connected and Namada app is open on the device, the CLI can interact with it.

## **4. Generate Address with Ledger**

To generate an address using your Ledger, run the following command in the CLI:

```bash
namada wallet address import ledger --alias <your-alias>
```

Replace `<your-alias>` with a name or alias for your wallet.

The command will communicate with your Ledger and generate a new address. You will be prompted to confirm the action on your Ledger device. Approve it to finish the process.

You can verify the address with the following command:

```bash
namada wallet address list
```

## **5. Signing Transactions with Ledger**

After setting up your wallet with Ledger, you can use it to sign transactions securely.

### Step 1: Staking with Ledger

To stake tokens using your Ledger, first check your available balance:

```bash
namada client balance <your-alias>
```

Then, stake tokens by running:

```bash
namada client bond --validator <validator-address> --amount <amount> --from <your-alias>
```

You will need to confirm this transaction on your Ledger. Review and approve the transaction directly from your device.

### Step 2: Sending Tokens with Ledger

To send tokens, use the following command:

```bash
namada client transfer --from <your-alias> --to <recipient-address> --amount <amount>
```

Again, you will be prompted to confirm the transaction on your Ledger device.

### Step 3: Claiming Rewards

To claim staking rewards, run the following:

```bash
namada client rewards claim --from <your-alias>
```

This will initiate a transaction for claiming rewards, and you’ll need to confirm the action on your Ledger.

## **6. Security Tips**

- Always ensure that your Ledger firmware and applications are up to date.
- Double-check addresses when signing transactions.
- Only connect your Ledger to trusted computers and use it in secure environments.
