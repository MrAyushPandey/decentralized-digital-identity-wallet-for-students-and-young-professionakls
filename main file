// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract DigitalIDWallet {
    struct Identity {
        string name;
        string email;
        string role; // e.g., student, intern, etc.
        bool exists;
    }

    mapping(address => Identity) private identities;

    // Register or update identity
    function setIdentity(string calldata name, string calldata email, string calldata role) external {
        identities[msg.sender] = Identity(name, email, role, true);
    }

    // View your identity
    function getMyIdentity() external view returns (string memory, string memory, string memory) {
        require(identities[msg.sender].exists, "Identity not set.");
        Identity memory id = identities[msg.sender];
        return (id.name, id.email, id.role);
    }
}
