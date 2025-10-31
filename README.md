# Solana Validator Client Ids

## Overview

The Solana gossip protocol requires each validator client to report a unique client identifier. These identifiers are used in gossip contact info messages to distinguish between different validator client implementations.

A client identifier is a **16-bit, little endian unsigned integer** (range: 0-65535). All Solana validator clients must implement the same set of identifiers as defined in [client-ids.csv](client-ids.csv).

## Requesting a New Client Identifier

### Prerequisites

A new client identifier request should meet the following criteria:

- The request comes from a team that is building and supporting a **materially new** validator client implementation
- The client is **open source**
- The client has (or plans to have) **some percentage of stake** on Solana mainnet-beta

### Step-by-Step Process

1. **Review existing identifiers**: Check [client-ids.csv](client-ids.csv) to see which IDs are already assigned.

2. **Choose the next available ID**: Use the lowest available integer that hasn't been assigned. IDs should be assigned sequentially where possible.

3. **Create a pull request** with the following changes:
   - Add a new row to `client-ids.csv` with your chosen `client_id` and `client_name`
   - Follow the CSV format: `client_id,client_name`
   - Keep entries sorted by `client_id` (ascending)

4. **Include in your PR description**:
   - Brief description of your validator client
   - Link to the open source repository
   - Current mainnet-beta stake percentage (if applicable)
   - Any other relevant information about your client

5. **Post PR Merge, Contact Other Clients**
   - You are encouraged to make a PR to existing clients and link to your accepted PR.


## Existing Client Requirements

All existing Solana validator clients are **expected** to monitor this repository and implement any changes to `client-ids.csv` as soon as possible in their client codebase.  Net new clients are encouraged to make a pull reqeust to the existing validator clients and link to the merged pull request from this repository.
