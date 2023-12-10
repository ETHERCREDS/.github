# .github
"Unlocking Developer Potential: Ethercreds - Where Anonymity Meets Brilliance, Revolutionizing Resumes with Zero-Knowledge Proofs, Ethereum Magic, and IPFS Wizardry!"

EtherCreds is an innovative decentralized platform for resume verification, harnessing the power of zero-knowledge proofs (zk-SNARKs), the Ethereum blockchain, and the InterPlanetary File System (IPFS). This platform is engineered to transform the landscape of talent discovery and validation, all the while prioritizing privacy and bolstering security.
techstack used:
Frontend: React and Next.js 
Backend: Node.js 
Smart Contracts: Solidity
GraphQL APIs: Custom Subgraphs with The Graph
Authentication: OAuth (GitHub)
IPFS Storage: Client Library

contracts are deployed on the these respective networks:
scroll:0x7391ba62C8A0E6F94e9BC86009C6F975c62F139a
polygon zkevm testnet:0x7391ba62C8A0E6F94e9BC86009C6F975c62F139a
polygon mumbai testnet:0x9a4164C18B830F1AF28474B0BB88C1249f932d1e


User Authentication

Users seamlessly log in using their GitHub or WorldID accounts via OAuth, tapping into the power of EtherCreds. This enables the platform to fetch pertinent data through the GitHub GraphQL API or verify their unique human status with WorldID. The system is flexible, allowing the integration of additional modules based on user demand for diverse credibility sources.

User Registration

Upon creating their profile, users are issued a unique ERC-721 resume token via EtherCreds. Unregistered users won't possess an ERC-721 token, and each user is limited to one token per module.

Resume Generation

Users can tailor their resumes by selecting specific criteria unique to each module. For instance, GitHub-based criteria trigger the backend to generate Zero-Knowledge Proofs (ZK proofs) for each criterion, ensuring data verification without compromising sensitive information.

Serialize ZK Proofs

Generated ZK proofs are converted into a suitable format, such as a JSON object.

Add ZK Proofs to IPFS

ZK proofs are seamlessly uploaded to IPFS using a client library, with IPFS returning a Content Identifier (CID) for the uploaded proofs.

Store the CID On-Chain

A MetaMask transaction is initiated to store the CID in the corresponding smart contract, depending on the module (GitHub, WorldID). This associates the CID with the user's Ethereum address, and an ERC-721 token is minted for the user. The minted ERC-721 serves as a comprehensive repository for all resume information, paving the way for other platforms to build atop EtherCreds.

User Profile

The platform showcases the user's generated resumes and associated ZK proofs, empowering users to view, edit, delete, and manage their data effortlessly.

Resume Verification

Users can input the Ethereum address or a unique proof identifier to verify a resume. The frontend fetches the associated CID from the relevant smart contract, retrieves the ZK proofs from IPFS, and validates their authenticity through the Verifier.sol smart contract.

Connect with Anon Devs powered by Push Protocol

Integrated into EtherCreds, Push facilitates potential employers in reaching out and engaging in discussions with anonymous developers. This feature enhances collaboration and communication after employers review developers' resumes on the app.
