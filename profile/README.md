### Warhead: Treasure Hunt and Community Game

![splash_new](https://github.com/Crypto-Warheads/.github/assets/39233126/7f51f605-8662-48cb-8a94-49c3c710c16b)


#### Overview
Warhead is an interactive treasure hunt and community game designed to engage users in two modes: Open Drop and Friend-to-Friend Drop. The game leverages geolocation to create immersive and fun experiences for both individual users and groups.

---

### Deployment
The smart contracts for Warhead have been deployed on Linea Mainnet and Mantle Mainnet.

### Contracts

1. **WarheadFactory**
2. **WarheadNft**
3. **ERC6551Account**
4. **ERC6551Registry**
5. **LocationRegistry**

#### WarheadFactory.sol
The `WarheadFactory` contract manages the creation, launching, and claiming of warheads.

#### WarheadNft.sol
The `WarheadNft` contract implements an ERC721 token representing the warhead and uses `ERC6551Registry` for creating token-bound smart accounts to hold rewards.

---

### Deployment Addresses

| Network       | Forwarder Address                             | WarheadFactory Address                           | WarheadNft Address                               | ERC6551Account Address                          | ERC6551Registry Address                          | LocationRegistry Address                        |
|---------------|-----------------------------------------------|--------------------------------------------------|--------------------------------------------------|------------------------------------------------|-------------------------------------------------|-------------------------------------------------|
| Linea Mainnet | 0x98b898ee7e62D1b0af50fD0fd653020D25bfe2F1    | 0x67744580E1ffC939e7DaE8B9c7F3899B0667d8A8       | [Address Needed]                                 | [Address Needed]                                | [Address Needed]                                 | [Address Needed]                                |
| Mantle Mainnet| 0x5f664fA188E0ae1aF0410842AB30b24d06a325a9    | 0x722368b00248032a00e6BB0BB0B9d1C6c91AA5d5       | [Address Needed]                                 | [Address Needed]                                | [Address Needed]                                 | [Address Needed]                                |
| Other Network | 0x0c197ccb1A0D9638d1db127A35CEFD5a9064Aa2F    | 0x722368b00248032a00e6BB0BB0B9d1C6c91AA5d5       | [Address Needed]                                 | [Address Needed]                                | [Address Needed]                                 | [Address Needed]                                |

---

### Features

- **Open Drop Mode**
  - Drop a warhead at a specific location filled with rewards.
  - People present at that location at the specified time can collect the reward.

- **Friend-to-Friend Drop Mode**
  - Send money or rewards to a friend by dropping a warhead at a specific location.
  - The friend must go to the designated location to collect the reward.

---

### Events

- `WarheadCreated(uint256 warheadId, address dropper, address warheadAddress)`
- `WarheadCreatedWithReceiver(uint256 warheadId, address dropper, address warheadAddress, address targetReceiver)`
- `WarheadDropped(uint256 warheadId, int256 targetLat, int256 targetLong, uint256 impactTime)`
- `WarheadClaimed(uint256 warheadId, address claimer, uint256 claimedAt)`

---

### Usage

#### Creating a Warhead
To create a new warhead, call the `createWarhead` function with the target receiver's address.

```solidity
function createWarhead(address targetReceiver) external;
```

#### Dropping a Warhead
To drop a warhead at a specific location, call the `dropWarhead` function with the warhead ID, coordinates, and impact time.

```solidity
function dropWarhead(uint256 warheadId, Coord memory coord, uint256 impactTime) external;
```

#### Claiming a Warhead
To claim a warhead, call the `claim` function with the location coordinates and warhead ID.

```solidity
function claim(Coord calldata location, uint256 warheadId) external;
```

#### Fetching Warhead Info
To fetch the information of a specific warhead, call the `fetchWarheadInfo` function with the warhead ID.

```solidity
function fetchWarheadInfo(uint256 warheadId) public view returns (WarheadObject memory);
```

---

### Subgraph and Substream

#### Subgraph
The subgraph for this project is deployed on The Graph Protocol and can be accessed via the following link:
- [Warheads Subgraph](https://api.studio.thegraph.com/query/77223/warheads/v0.0.1)

#### Substream
The substream for this project is available at:
- [Warheads Substream](https://srv.streamingfast.io/4aec28fa/graphql)

---

### Security

- The contracts use `Ownable` for access control.
- Geolocation and time checks ensure the integrity of the game mechanics.
- The WarheadNft contract secures rewards using ERC6551 token-bound smart accounts.

---

### Contact

For security issues or inquiries, please contact: [contact@yashgoyal.dev](mailto:contact@yashgoyal.dev)

---


### License

This project is licensed under the MIT License.

---

### Acknowledgements

This project utilizes OpenZeppelin's smart contract library for secure and reliable contract development.

---

### Disclaimer

Use the contracts at your own risk. The authors are not responsible for any loss of funds or damages incurred from using these contracts.
