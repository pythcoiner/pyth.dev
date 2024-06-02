# How Liana works?

## Create the setup (P2WSH)

|- Alice (No timelock)    ->     [d7ea29a1/48'/1'/0'/2']xpub_alice
|- Bob + 2 blocks         ->     [d4ab66f1/48'/1'/0'/2']xpub_bob

Descriptor:

wsh(
  or_d(
    pk([d7ea29a1/48'/1'/0'/2']xpub_alice/<0;1>/*),
    and_v(
      v:pkh([d4ab66f1/48'/1'/0'/2']xpub_bob/<0;1>/*),
      older(2)
    )
  )
)#jmr6ege0

## Fund the wallet:

Receive address at index 0: tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6

Funding tx: 
tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6
020000000181ff8f7b4c17bbb8e9f981ec95e4e64e4cb64f42afb8362f70b65e773aa1034c000000006a473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28dfdffffff02d3494c00000000001976a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac404b4c0000000000220020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee00000000

## Spend the coin via Alice path:

Receiver address: tb1p6raxppjgjcu244kdrp4fay8f4weuzkzp63dlkkl2q48wds5m8hzqc9eh33

Unsigned PSBT: cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAD9////AbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4BBUEhAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkrHNkdqkUV03BrPPy2diBqWgxD9b8sosZzaCIrVKyaCIGAhh4dU5fL2KmkjhD4VPkfkgIDjLSLAHpTy7pmdzNNY6XHNSrZvEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAiBgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZBzX6imhMAAAgAEAAIAAAACAAgAAgAAAAAAAAAAAAAA=

Signed(Alice) PSBT: cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAD9////AbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4iAgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZEcwRAIgQVHDIMpU31meK1gBF84EIS1mj7bpcY2cQXNOIDh2YZoCIFJW8TlWGtIUGYfLUTU/dA92Zj64T8QsPbfNSAWl0xMcAQEFQSEDJyUTnUnx+tPZf7dHse6BMY5UQrJgoTemoUMhp5IrmmSsc2R2qRRXTcGs8/LZ2IGpaDEP1vyyixnNoIitUrJoIgYCGHh1Tl8vYqaSOEPhU+R+SAgOMtIsAelPLumZ3M01jpcc1Ktm8TAAAIABAACAAAAAgAIAAIAAAAAAAAAAACIGAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkHNfqKaEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAAAA==

## Spend the coin via Bob path:

Receiver address: tb1p6raxppjgjcu244kdrp4fay8f4weuzkzp63dlkkl2q48wds5m8hzqc9eh33

Unsigned PSBT: cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAACAAAAAbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4BBUEhAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkrHNkdqkUV03BrPPy2diBqWgxD9b8sosZzaCIrVKyaCIGAhh4dU5fL2KmkjhD4VPkfkgIDjLSLAHpTy7pmdzNNY6XHNSrZvEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAiBgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZBzX6imhMAAAgAEAAIAAAACAAgAAgAAAAAAAAAAAAAA=

Signed(Bob) PSBT: cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAACAAAAAbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4iAgIYeHVOXy9ippI4Q+FT5H5ICA4y0iwB6U8u6ZnczTWOl0gwRQIhANJXsvWQEPRV3CdWTWxpbwv/BBdMPKyR1egn6dMF9VzYAiA3qZ3CAD3CTQ8MMxFRhBdM4jzVeBd54eh7e1qgBD6/qAEBBUEhAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkrHNkdqkUV03BrPPy2diBqWgxD9b8sosZzaCIrVKyaCIGAhh4dU5fL2KmkjhD4VPkfkgIDjLSLAHpTy7pmdzNNY6XHNSrZvEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAiBgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZBzX6imhMAAAgAEAAIAAAACAAgAAgAAAAAAAAAAAAAA=

## Decode funding transaction:

```shell
~ ❯ bitcoin-cli -signet decoderawtransaction 020000000181ff8f7b4c17bbb8e9f981ec95e4e64e4cb64f42afb8362f70b65e773aa1034c000000006a473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28dfdffffff02d3494c00000000001976a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac404b4c0000000000220020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee00000000

{
  "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
  "hash": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
  "version": 2,
  "size": 234,
  "vsize": 234,
  "weight": 936,
  "locktime": 0,
  "vin": [
    {
      "txid": "4c03a13a775eb6702f36b8af424fb64c4ee6e495ec81f9e9b8bb174c7b8fff81",
      "vout": 0,
      "scriptSig": {
        "asm": "3044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e80742[ALL] 027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d",
        "hex": "473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d"
      },
      "sequence": 4294967293
    }
  ],
  "vout": [
    {
      "value": 0.04999635,
      "n": 0,
      "scriptPubKey": {
        "asm": "OP_DUP OP_HASH160 7233fb1d220a5c1d55ac5fe461f2aaa26feae545 OP_EQUALVERIFY OP_CHECKSIG",
        "desc": "addr(mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn)#rpux6tau",
        "hex": "76a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac",
        "address": "mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn",
        "type": "pubkeyhash"
      }
    },
    {
      "value": 0.05000000,
      "n": 1,
      "scriptPubKey": {
        "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
        "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
        "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
        "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
        "type": "witness_v0_scripthash"
      }
    }
  ]
}
```

## Decode Alice PSBT:

### Unsigned:

```shell
~ ❯ bitcoin-cli -signet decodepsbt cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAD9////AbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4BBUEhAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkrHNkdqkUV03BrPPy2diBqWgxD9b8sosZzaCIrVKyaCIGAhh4dU5fL2KmkjhD4VPkfkgIDjLSLAHpTy7pmdzNNY6XHNSrZvEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAiBgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZBzX6imhMAAAgAEAAIAAAACAAgAAgAAAAAAAAAAAAAA=

{
  "tx": {
    "txid": "8c1ae3c637ed46db4479110cdece0a34beae61def424202808ea559ff2d13eeb",
    "hash": "8c1ae3c637ed46db4479110cdece0a34beae61def424202808ea559ff2d13eeb",
    "version": 2,
    "size": 94,
    "vsize": 94,
    "weight": 376,
    "locktime": 0,
    "vin": [
      {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "vout": 1,
        "scriptSig": {
          "asm": "",
          "hex": ""
        },
        "sequence": 4294967293
      }
    ],
    "vout": [
      {
        "value": 0.04999861,
        "n": 0,
        "scriptPubKey": {
          "asm": "1 d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "desc": "rawtr(d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4)#4tsqqc4l",
          "hex": "5120d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "address": "tb1p6raxppjgjcu244kdrp4fay8f4weuzkzp63dlkkl2q48wds5m8hzqc9eh33",
          "type": "witness_v1_taproot"
        }
      }
    ]
  },
  "global_xpubs": [
  ],
  "psbt_version": 0,
  "proprietary": [
  ],
  "unknown": {
  },
  "inputs": [
    {
      "witness_utxo": {
        "amount": 0.05000000,
        "scriptPubKey": {
          "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
          "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
          "type": "witness_v0_scripthash"
        }
      },
      "non_witness_utxo": {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "hash": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "version": 2,
        "size": 234,
        "vsize": 234,
        "weight": 936,
        "locktime": 0,
        "vin": [
          {
            "txid": "4c03a13a775eb6702f36b8af424fb64c4ee6e495ec81f9e9b8bb174c7b8fff81",
            "vout": 0,
            "scriptSig": {
              "asm": "3044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e80742[ALL] 027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d",
              "hex": "473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d"
            },
            "sequence": 4294967293
          }
        ],
        "vout": [
          {
            "value": 0.04999635,
            "n": 0,
            "scriptPubKey": {
              "asm": "OP_DUP OP_HASH160 7233fb1d220a5c1d55ac5fe461f2aaa26feae545 OP_EQUALVERIFY OP_CHECKSIG",
              "desc": "addr(mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn)#rpux6tau",
              "hex": "76a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac",
              "address": "mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn",
              "type": "pubkeyhash"
            }
          },
          {
            "value": 0.05000000,
            "n": 1,
            "scriptPubKey": {
              "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
              "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
              "type": "witness_v0_scripthash"
            }
          }
        ]
      },
      "witness_script": {
        "asm": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64 OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 574dc1acf3f2d9d881a968310fd6fcb28b19cda0 OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF",
        "hex": "21032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64ac736476a914574dc1acf3f2d9d881a968310fd6fcb28b19cda088ad52b268",
        "type": "nonstandard"
      },
      "bip32_derivs": [
        {
          "pubkey": "021878754e5f2f62a6923843e153e47e48080e32d22c01e94f2ee999dccd358e97",
          "master_fingerprint": "d4ab66f1",
          "path": "m/48h/1h/0h/2h/0/0"
        },
        {
          "pubkey": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64",
          "master_fingerprint": "d7ea29a1",
          "path": "m/48h/1h/0h/2h/0/0"
        }
      ]
    }
  ],
  "outputs": [
    {
    }
  ],
  "fee": 0.00000139
}

```

### Signed

```shell
~ ❯ bitcoin-cli -signet decodepsbt cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAD9////AbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4iAgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZEcwRAIgQVHDIMpU31meK1gBF84EIS1mj7bpcY2cQXNOIDh2YZoCIFJW8TlWGtIUGYfLUTU/dA92Zj64T8QsPbfNSAWl0xMcAQEFQSEDJyUTnUnx+tPZf7dHse6BMY5UQrJgoTemoUMhp5IrmmSsc2R2qRRXTcGs8/LZ2IGpaDEP1vyyixnNoIitUrJoIgYCGHh1Tl8vYqaSOEPhU+R+SAgOMtIsAelPLumZ3M01jpcc1Ktm8TAAAIABAACAAAAAgAIAAIAAAAAAAAAAACIGAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkHNfqKaEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAAAA==


{
  "tx": {
    "txid": "8c1ae3c637ed46db4479110cdece0a34beae61def424202808ea559ff2d13eeb",
    "hash": "8c1ae3c637ed46db4479110cdece0a34beae61def424202808ea559ff2d13eeb",
    "version": 2,
    "size": 94,
    "vsize": 94,
    "weight": 376,
    "locktime": 0,
    "vin": [
      {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "vout": 1,
        "scriptSig": {
          "asm": "",
          "hex": ""
        },
        "sequence": 4294967293
      }
    ],
    "vout": [
      {
        "value": 0.04999861,
        "n": 0,
        "scriptPubKey": {
          "asm": "1 d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "desc": "rawtr(d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4)#4tsqqc4l",
          "hex": "5120d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "address": "tb1p6raxppjgjcu244kdrp4fay8f4weuzkzp63dlkkl2q48wds5m8hzqc9eh33",
          "type": "witness_v1_taproot"
        }
      }
    ]
  },
  "global_xpubs": [
  ],
  "psbt_version": 0,
  "proprietary": [
  ],
  "unknown": {
  },
  "inputs": [
    {
      "witness_utxo": {
        "amount": 0.05000000,
        "scriptPubKey": {
          "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
          "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
          "type": "witness_v0_scripthash"
        }
      },
      "non_witness_utxo": {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "hash": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "version": 2,
        "size": 234,
        "vsize": 234,
        "weight": 936,
        "locktime": 0,
        "vin": [
          {
            "txid": "4c03a13a775eb6702f36b8af424fb64c4ee6e495ec81f9e9b8bb174c7b8fff81",
            "vout": 0,
            "scriptSig": {
              "asm": "3044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e80742[ALL] 027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d",
              "hex": "473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d"
            },
            "sequence": 4294967293
          }
        ],
        "vout": [
          {
            "value": 0.04999635,
            "n": 0,
            "scriptPubKey": {
              "asm": "OP_DUP OP_HASH160 7233fb1d220a5c1d55ac5fe461f2aaa26feae545 OP_EQUALVERIFY OP_CHECKSIG",
              "desc": "addr(mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn)#rpux6tau",
              "hex": "76a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac",
              "address": "mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn",
              "type": "pubkeyhash"
            }
          },
          {
            "value": 0.05000000,
            "n": 1,
            "scriptPubKey": {
              "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
              "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
              "type": "witness_v0_scripthash"
            }
          }
        ]
      },
      "partial_signatures": {
        "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64": "304402204151c320ca54df599e2b580117ce04212d668fb6e9718d9c41734e203876619a02205256f139561ad2141987cb51353f740f76663eb84fc42c3db7cd4805a5d3131c01"
      },
      "witness_script": {
        "asm": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64 OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 574dc1acf3f2d9d881a968310fd6fcb28b19cda0 OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF",
        "hex": "21032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64ac736476a914574dc1acf3f2d9d881a968310fd6fcb28b19cda088ad52b268",
        "type": "nonstandard"
      },
      "bip32_derivs": [
        {
          "pubkey": "021878754e5f2f62a6923843e153e47e48080e32d22c01e94f2ee999dccd358e97",
          "master_fingerprint": "d4ab66f1",
          "path": "m/48h/1h/0h/2h/0/0"
        },
        {
          "pubkey": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64",
          "master_fingerprint": "d7ea29a1",
          "path": "m/48h/1h/0h/2h/0/0"
        }
      ]
    }
  ],
  "outputs": [
    {
    }
  ],
  "fee": 0.00000139
}
```

## Decode Bob PSBT:

### Unsigned:

```shell
~ ❯ bitcoin-cli -signet decodepsbt cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAACAAAAAbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4BBUEhAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkrHNkdqkUV03BrPPy2diBqWgxD9b8sosZzaCIrVKyaCIGAhh4dU5fL2KmkjhD4VPkfkgIDjLSLAHpTy7pmdzNNY6XHNSrZvEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAiBgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZBzX6imhMAAAgAEAAIAAAACAAgAAgAAAAAAAAAAAAAA=
{
  "tx": {
    "txid": "abcc3bc335612f81386479fe3d95973674936e1771a50bd5fcd73a24beb9b3a8",
    "hash": "abcc3bc335612f81386479fe3d95973674936e1771a50bd5fcd73a24beb9b3a8",
    "version": 2,
    "size": 94,
    "vsize": 94,
    "weight": 376,
    "locktime": 0,
    "vin": [
      {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "vout": 1,
        "scriptSig": {
          "asm": "",
          "hex": ""
        },
        "sequence": 2
      }
    ],
    "vout": [
      {
        "value": 0.04999861,
        "n": 0,
        "scriptPubKey": {
          "asm": "1 d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "desc": "rawtr(d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4)#4tsqqc4l",
          "hex": "5120d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "address": "tb1p6raxppjgjcu244kdrp4fay8f4weuzkzp63dlkkl2q48wds5m8hzqc9eh33",
          "type": "witness_v1_taproot"
        }
      }
    ]
  },
  "global_xpubs": [
  ],
  "psbt_version": 0,
  "proprietary": [
  ],
  "unknown": {
  },
  "inputs": [
    {
      "witness_utxo": {
        "amount": 0.05000000,
        "scriptPubKey": {
          "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
          "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
          "type": "witness_v0_scripthash"
        }
      },
      "non_witness_utxo": {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "hash": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "version": 2,
        "size": 234,
        "vsize": 234,
        "weight": 936,
        "locktime": 0,
        "vin": [
          {
            "txid": "4c03a13a775eb6702f36b8af424fb64c4ee6e495ec81f9e9b8bb174c7b8fff81",
            "vout": 0,
            "scriptSig": {
              "asm": "3044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e80742[ALL] 027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d",
              "hex": "473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d"
            },
            "sequence": 4294967293
          }
        ],
        "vout": [
          {
            "value": 0.04999635,
            "n": 0,
            "scriptPubKey": {
              "asm": "OP_DUP OP_HASH160 7233fb1d220a5c1d55ac5fe461f2aaa26feae545 OP_EQUALVERIFY OP_CHECKSIG",
              "desc": "addr(mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn)#rpux6tau",
              "hex": "76a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac",
              "address": "mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn",
              "type": "pubkeyhash"
            }
          },
          {
            "value": 0.05000000,
            "n": 1,
            "scriptPubKey": {
              "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
              "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
              "type": "witness_v0_scripthash"
            }
          }
        ]
      },
      "witness_script": {
        "asm": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64 OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 574dc1acf3f2d9d881a968310fd6fcb28b19cda0 OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF",
        "hex": "21032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64ac736476a914574dc1acf3f2d9d881a968310fd6fcb28b19cda088ad52b268",
        "type": "nonstandard"
      },
      "bip32_derivs": [
        {
          "pubkey": "021878754e5f2f62a6923843e153e47e48080e32d22c01e94f2ee999dccd358e97",
          "master_fingerprint": "d4ab66f1",
          "path": "m/48h/1h/0h/2h/0/0"
        },
        {
          "pubkey": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64",
          "master_fingerprint": "d7ea29a1",
          "path": "m/48h/1h/0h/2h/0/0"
        }
      ]
    }
  ],
  "outputs": [
    {
    }
  ],
  "fee": 0.00000139
}
```

### Signed:

```shell
~ ❯ bitcoin-cli -signet decodepsbt cHNidP8BAF4CAAAAAftQLWvVAxW8iGeJ56r9oDUiWTaXb4+ucMQXlqWyMjJyAQAAAAACAAAAAbVKTAAAAAAAIlEg0PpghkiWOKrWzRhqnpDpq7PBWEHUW/tb6gVO5sKbPcQAAAAAAAEA6gIAAAABgf+Pe0wXu7jp+YHsleTmTky2T0KvuDYvcLZedzqhA0wAAAAAakcwRAIgZO+7J75T+DxYus/631RPjweMTX0ef71VyryG1I3vwioCIAmEpEWfuQzCPfE/6XijeaHFqLXBKflu+kwN4uI36AdCASECfPduaO9J6Rmd0nmxrVitLB689w5i29U0pjtup3UY4o39////AtNJTAAAAAAAGXapFHIz+x0iClwdVaxf5GHyqqJv6uVFiKxAS0wAAAAAACIAIERcUYEhVx+xHcjU1v8HtV6Yn1q0j4c15Jg9/vPmbY3uAAAAAAEBK0BLTAAAAAAAIgAgRFxRgSFXH7EdyNTW/we1XpifWrSPhzXkmD3+8+Ztje4iAgIYeHVOXy9ippI4Q+FT5H5ICA4y0iwB6U8u6ZnczTWOl0gwRQIhANJXsvWQEPRV3CdWTWxpbwv/BBdMPKyR1egn6dMF9VzYAiA3qZ3CAD3CTQ8MMxFRhBdM4jzVeBd54eh7e1qgBD6/qAEBBUEhAyclE51J8frT2X+3R7HugTGOVEKyYKE3pqFDIaeSK5pkrHNkdqkUV03BrPPy2diBqWgxD9b8sosZzaCIrVKyaCIGAhh4dU5fL2KmkjhD4VPkfkgIDjLSLAHpTy7pmdzNNY6XHNSrZvEwAACAAQAAgAAAAIACAACAAAAAAAAAAAAiBgMnJROdSfH609l/t0ex7oExjlRCsmChN6ahQyGnkiuaZBzX6imhMAAAgAEAAIAAAACAAgAAgAAAAAAAAAAAAAA=


{
  "tx": {
    "txid": "abcc3bc335612f81386479fe3d95973674936e1771a50bd5fcd73a24beb9b3a8",
    "hash": "abcc3bc335612f81386479fe3d95973674936e1771a50bd5fcd73a24beb9b3a8",
    "version": 2,
    "size": 94,
    "vsize": 94,
    "weight": 376,
    "locktime": 0,
    "vin": [
      {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "vout": 1,
        "scriptSig": {
          "asm": "",
          "hex": ""
        },
        "sequence": 2
      }
    ],
    "vout": [
      {
        "value": 0.04999861,
        "n": 0,
        "scriptPubKey": {
          "asm": "1 d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "desc": "rawtr(d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4)#4tsqqc4l",
          "hex": "5120d0fa6086489638aad6cd186a9e90e9abb3c15841d45bfb5bea054ee6c29b3dc4",
          "address": "tb1p6raxppjgjcu244kdrp4fay8f4weuzkzp63dlkkl2q48wds5m8hzqc9eh33",
          "type": "witness_v1_taproot"
        }
      }
    ]
  },
  "global_xpubs": [
  ],
  "psbt_version": 0,
  "proprietary": [
  ],
  "unknown": {
  },
  "inputs": [
    {
      "witness_utxo": {
        "amount": 0.05000000,
        "scriptPubKey": {
          "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
          "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
          "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
          "type": "witness_v0_scripthash"
        }
      },
      "non_witness_utxo": {
        "txid": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "hash": "723232b2a59617c470ae8f6f9736592235a0fdaae7896788bc1503d56b2d50fb",
        "version": 2,
        "size": 234,
        "vsize": 234,
        "weight": 936,
        "locktime": 0,
        "vin": [
          {
            "txid": "4c03a13a775eb6702f36b8af424fb64c4ee6e495ec81f9e9b8bb174c7b8fff81",
            "vout": 0,
            "scriptSig": {
              "asm": "3044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e80742[ALL] 027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d",
              "hex": "473044022064efbb27be53f83c58bacffadf544f8f078c4d7d1e7fbd55cabc86d48defc22a02200984a4459fb90cc23df13fe978a379a1c5a8b5c129f96efa4c0de2e237e807420121027cf76e68ef49e9199dd279b1ad58ad2c1ebcf70e62dbd534a63b6ea77518e28d"
            },
            "sequence": 4294967293
          }
        ],
        "vout": [
          {
            "value": 0.04999635,
            "n": 0,
            "scriptPubKey": {
              "asm": "OP_DUP OP_HASH160 7233fb1d220a5c1d55ac5fe461f2aaa26feae545 OP_EQUALVERIFY OP_CHECKSIG",
              "desc": "addr(mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn)#rpux6tau",
              "hex": "76a9147233fb1d220a5c1d55ac5fe461f2aaa26feae54588ac",
              "address": "mqvobcuU1K8ZhEuuMQd4ztq611WYpqPAUn",
              "type": "pubkeyhash"
            }
          },
          {
            "value": 0.05000000,
            "n": 1,
            "scriptPubKey": {
              "asm": "0 445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "desc": "addr(tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6)#l5s83tep",
              "hex": "0020445c518121571fb11dc8d4d6ff07b55e989f5ab48f8735e4983dfef3e66d8dee",
              "address": "tb1qg3w9rqfp2u0mz8wg6nt07pa4t6vf7k4537rnteyc8hl08end3hhq9zamm6",
              "type": "witness_v0_scripthash"
            }
          }
        ]
      },
      "partial_signatures": {
        "021878754e5f2f62a6923843e153e47e48080e32d22c01e94f2ee999dccd358e97": "3045022100d257b2f59010f455dc27564d6c696f0bff04174c3cac91d5e827e9d305f55cd8022037a99dc2003dc24d0f0c33115184174ce23cd5781779e1e87b7b5aa0043ebfa801"
      },
      "witness_script": {
        "asm": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64 OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 574dc1acf3f2d9d881a968310fd6fcb28b19cda0 OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF",
        "hex": "21032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64ac736476a914574dc1acf3f2d9d881a968310fd6fcb28b19cda088ad52b268",
        "type": "nonstandard"
      },
      "bip32_derivs": [
        {
          "pubkey": "021878754e5f2f62a6923843e153e47e48080e32d22c01e94f2ee999dccd358e97",
          "master_fingerprint": "d4ab66f1",
          "path": "m/48h/1h/0h/2h/0/0"
        },
        {
          "pubkey": "032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64",
          "master_fingerprint": "d7ea29a1",
          "path": "m/48h/1h/0h/2h/0/0"
        }
      ]
    }
  ],
  "outputs": [
    {
    }
  ],
  "fee": 0.00000139
}
```

Lets analyse the script of recovery Tx:

```
032725139d49f1fad3d97fb747b1ee81318e5442b260a137a6a14321a7922b9a64 OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
```

#### Stack execution:

 - 0 - Init: (stack is empty)

                SIG BOB_PUBKEY OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF 
|______________|

- 1 - SIG and BOB_PUBKEY load on the stack:

                OP_CHECKSIG OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 SCRIPT HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|  BOB_PUBKEY  |
|      SIG     |
|______________|


                OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|  OP_CHECKSIG |
|  BOB_PUBKEY  |
|      SIG     |
|______________|

                OP_IFDUP OP_NOTIF OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|       1      |
|______________|

                OP_NOTIF OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|  OP_IFDUP    |
|       1      |
|______________|

                OP_NOTIF OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|       1      |
|       1      |
|______________|

                 OP_DUP OP_HASH160 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|   OP_NOTIF   |
|       1      |
|       1      |
|______________|

// What do we hashs here? the script

                 SCRIPT_HASH OP_EQUALVERIFY OP_CHECKSIGVERIFY 2 OP_CHECKSEQUENCEVERIFY OP_ENDIF
|   OP_HASH160 |
|       1      |
|       1      |
|______________|



