1. Deploy contract safe-singleton-factory: có bytecode là 0x604580600e600039806000f350fe7fffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffe03601600081602082378035828234f58015156039578182fd5b8082525050506014600cf3
2. Install package: yarn add @gnosis.pm/safe-singleton-factory  
   Create file node-modules/@gnosis.pm/safe-singleton-factory/artifacts/11115/deployment.json với nội dung:
   {
   "gasPrice": 100000000000,
   "gasLimit": 100000,
   "signerAddress": "0x7500d14588aca06855b635b30d360c29575a8f27”, // địa chỉ deploy safe-singleton-factory
   "transaction": "0xf8a58085174876e800830186a08080b853604580600e600039806000f350fe7fffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffe03601600081602082378035828234f58015156039578182fd5b8082525050506014600cf32ca0c39cd41588456865453604a6bcfe26b9e5185b435d2535d8b065265d6cd82f71a036c5b462321656f53c06a6f9e017487ab49a67b47d2dcf34e0b4dc7a1e225380",
   "address": "0xbfbe42590568533334b699cef5e9879abb8f32e3”    // địa chỉ contract safe-singleton-factory
   }
3. Config astra network trong hardhat.config.ts với chainId 11115
   astra: {
   accounts: [PK ? PK : ""],
   url: `https://rpc.astranaut.dev/`,
   timeout: 8000000,
   gasPrice: 20000000000,
   chainId: 11115,
   },
4. Set env CUSTOM_DETERMINISTIC_DEPLOYMENT=true
5. Run: yarn deploy-all astra
