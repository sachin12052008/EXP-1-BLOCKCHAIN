### Experiment 1: Decentralized Certificate Verification
## Aim:
  To develop a smart contract for issuing and verifying academic certificates on Ethereum, preventing forgery and ensuring authenticity.
## Algorithm:
1. Deploy a smart contract where universities can issue certificates.
2. Store a hash of certificate data on-chain.
3. Provide a verification function that checks certificate authenticity.
4. Users can verify the certificate by comparing the stored hash.
## Program:
```
DEVELOPED BY:SACHIN J M
REG NO:212225100041
```
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;
contract CertificateVerification {
address public university;
mapping(bytes32 => bool) public certificates; // Store hashed certificates
event CertificateIssued(bytes32 indexed certHash);
constructor() {
university = msg.sender; // University deploys the contract
}
function issueCertificate(string memory studentName, string memory degree, uint256 year) public {
require(msg.sender == university, "Only university can issue certificates");
bytes32 certHash = keccak256(abi.encodePacked(studentName, degree, year));
certificates[certHash] = true;
emit CertificateIssued(certHash);
}
function verifyCertificate(string memory studentName, string memory degree, uint256 year) public view returns (bool) {
bytes32 certHash = keccak256(abi.encodePacked(studentName, degree, year));
return certificates[certHash];
}
}
```
# Expected Output:
<img width="1575" height="1078" alt="Screenshot 2026-11-18 143401" src="https://github.com/user-attachments/assets/717e308c-06f3-43b6-bdb6-ae4182dcda93" />
<img width="1881" height="1078" alt="Screenshot 2026-11-18 143437" src="https://github.com/user-attachments/assets/f1f07a1a-0ea9-4f3b-9f48-b0d4ea095c0e" />
<img width="1913" height="1075" alt="Screenshot 2026-11-18 143449" src="https://github.com/user-attachments/assets/1f6c9272-90d7-4302-a5b4-5c2ddb822b27" />

# Result:
THE EXPERIMENT AND THE AIM TO VERIFY THE DECENTRALIZED CERTIFICATION DONE SUCCESSFULLY
