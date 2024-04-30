### serilization.py file
I have defined all the functions in serilization file here below.

dsha(tx): Performs a double SHA256 hash on the provided transaction data.
rev(buf): Reverses the bytes of the input hexadecimal string.
sha(tx): Computes the SHA256 hash of the input transaction data.
little_endian(num, num_bytes): Converts an integer to little-endian bytes.
Serelization(json_data): Serializes JSON transaction data into raw transaction data.
transaction_id(Raw_transaction_data): Computes the transaction ID (TXID) from raw transaction data.
remove_json(text): Removes ".json" from the provided text.
testing(txid, file_name_value): Checks if the SHA256 hash of a transaction ID matches a given value.
checking_ptr(transaction_json_data): Checks if the transaction uses P2TR (Pay to Taproot) scriptpubkeys.
total_fees_df(transaction_json_data): Calculates the total transaction fees.
wtxid_Serelization(json_data): Serializes JSON transaction data into raw transaction data with support for Witness data.

### block.py file
coinbase_txid_fn(coinbase_json_data): Computes the transaction ID (TXID) for the coinbase transaction.
merkleroot(Txid_list): Computes the Merkle root hash for a list of transaction IDs.
transaction_count(transaction_list): Computes the encoded transaction count for a list of transactions.
block(merkle_root, bits, nonce, transaction_count, coinbase_txid, transaction_list): Defines a Bitcoin block with its header and transactions.
block_header(version, previous_block_hash, merkle_root, nonce): Constructs the block header by assembling its components.
wtxid_commitment(wtxid_list): Computes the witness transaction ID (wTXID) commitment.

### main.py file
File Extraction: Extracts file names from a specified folder path (mempool).
Transaction Validation: Validates transactions by checking if their transaction IDs match their file names and if they adhere to specific transaction types (v1_p2tr).
Serialization: Serializes transaction data into raw transaction data and computes transaction IDs.
Writing Valid Files: Writes the names of valid transactions into a text file (Valid_p2tr_files.txt).
Block Construction: Constructs a Bitcoin block by computing the Merkle root, block header, and performing proof of work.
Writing Output: Writes the block header, coinbase transaction data, coinbase transaction ID, and valid transaction IDs into an output text file (output.txt).