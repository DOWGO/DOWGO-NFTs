# DOWGO-NFTs

// SPDX-License-Identifier: MIT
/**
________  ________  ___       __   ________  ________     
|\   ___ \|\   __  \|\  \     |\  \|\   ____\|\   __  \    
\ \  \_|\ \ \  \|\  \ \  \    \ \  \ \  \___|\ \  \|\  \   
 \ \  \ \\ \ \  \\\  \ \  \  __\ \  \ \  \  __\ \  \\\  \  
  \ \  \_\\ \ \  \\\  \ \  \|\__\_\  \ \  \|\  \ \  \\\  \ 
   \ \_______\ \_______\ \____________\ \_______\ \_______\
    \|_______|\|_______|\|____________|\|_______|\|_______|
*/                                                           
                                                          
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC1155/ERC1155.sol";
import "@openzeppelin/contracts/utils/Strings.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract DOWGOBOYZ_S22 is ERC1155, Ownable {

    constructor() ERC1155('ipfs://QmbM4CKAcpDumx5PDt4b56Z5jSQKx6dcErbfUrSjmp6vTL/{id}.json') {
        for(uint i = 1 ; i <= 108 ; i++) {
            _mint(msg.sender, i, 1, bytes(abi.encodePacked("DOWGOBOY#", Strings.toString(i))));
        }
    }

    function uri(uint _tokenId) override public pure returns(string memory) {
        return string (abi.encodePacked(
            "ipfs://QmbM4CKAcpDumx5PDt4b56Z5jSQKx6dcErbfUrSjmp6vTL/",
            Strings.toString(_tokenId),
            ".json"
        ));
    }

    function name() public pure returns(string memory) {
        string memory name = "DOWGOBOYZ S22";
        return name;
    }
}
