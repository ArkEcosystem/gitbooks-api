# Rounds

## List rounds data

### Endpoint

```text
/rounds/{roundNumber}/delegates
```

### Path parameters

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| roundNumber | int | The number of wanted round. | true |

### Example

```text
curl http://dexplorer.ark.io/api/rounds/5000/delegates
```

### Response

```javascript
{
    "data": [
        {
            "publicKey": "03bbfb43ecb5a54a1e227bb37b5812b5321213838d376e2b455b6af78442621dec",
            "votes": "50583674434334"
        },
        {
            "publicKey": "02215cbe21074d065f3d090f53284e8104c2dc6282ba50bf155adcdfdbcfe325d5",
            "votes": "1898260000000"
        },
        {
            "publicKey": "03a2f2ce2aebd426d353bf3abf2c00a85e3122070bbeaa04b73eba2a6119dbc620",
            "votes": "1877490000000"
        },
        {
            "publicKey": "02a1b28b59216ea270349c6be5881fba356cb324f320cb59b74a13f28588cce253",
            "votes": "1450200390050"
        },
        {
            "publicKey": "037997a6553ea8073eb199e9f5ff23b8f0892e79433ef35e13966e0a12849d02e3",
            "votes": "1341227716260"
        },
        {
            "publicKey": "0394685435d7331d178effe91d6b101ce7c4a6e03d2a96cfd5be1fffb0ae156e58",
            "votes": "1309880000000"
        },
        {
            "publicKey": "03d7a20b3d39b7526a5057a9b486f0200bc57543e69e5fa61d9ce0bdd7784162c3",
            "votes": "1099420000000"
        },
        {
            "publicKey": "03120f521f7025f76341a09112f88a6c072411c549e4bfa8c92946fcf1c57cdf1e",
            "votes": "1096370000110"
        },
        {
            "publicKey": "023ee98f453661a1cb765fd60df95b4efb1e110660ffb88ae31c2368a70f1f7359",
            "votes": "1093770000000"
        },
        {
            "publicKey": "033a5474f68f92f254691e93c06a2f22efaf7d66b543a53efcece021819653a200",
            "votes": "1091490000000"
        },
        {
            "publicKey": "0235d06f70a883b429446d7c461e07b6615feb0c34e152d7caf9f38b13ad4d6009",
            "votes": "1091289653466"
        },
        {
            "publicKey": "03d3c6889608074b44155ad2e6577c3368e27e6e129c457418eb3e5ed029544e8d",
            "votes": "1089450000000"
        },
        {
            "publicKey": "0236d5232cdbd1e7ab87fad10ebe689c4557bc9d0c408b6773be964c837231d5f0",
            "votes": "1088500000000"
        },
        {
            "publicKey": "030c0d642b9b5337d8f9f257e9e460bdd9d15e0581391896336dd8acb24b5d47b4",
            "votes": "1087610000000"
        },
        {
            "publicKey": "027716e659220085e41389efc7cf6a05f7f7c659cf3db9126caabce6cda9156582",
            "votes": "1086907719700"
        },
        {
            "publicKey": "02d2a18dcb0dd7abd0a91ca70cb79d04e1ff7a4e77d1d8beda3d6c0a51b55a5db1",
            "votes": "1082170000000"
        },
        {
            "publicKey": "0366da7ed85cc1e73a13fafb8007d2609d92239355847343cc7b12d85a65d25502",
            "votes": "1078280000000"
        },
        {
            "publicKey": "036f1cb6a811173e8d193e41a4ceb77253c3e4f2832e7a4ba3cf3f8f9e606f5f05",
            "votes": "1048152000000"
        },
        {
            "publicKey": "02d0244d939fad9004cc104f71b46b428d903e4f2988a65f39fdaa1b7482894c9e",
            "votes": "1029530000000"
        },
        {
            "publicKey": "0284a88da69cc04439633217c6961d2800df0f7dff7f85b9803848ee02d0743f1d",
            "votes": "1022220000000"
        },
        {
            "publicKey": "03ea97a59522c4cb4bb3420fc94555f6223813d9817dd421bf533b390a7ea140db",
            "votes": "1003040000000"
        },
        {
            "publicKey": "022ffb5fa4eb5b2e71c985b1d796642528802f04a6ddf9a449ba1aab292a9744aa",
            "votes": "1000280000000"
        },
        {
            "publicKey": "0259d9ca7922c277b0e7407a88703bbb98f5da43a335b0eefa6c4642f072acfe79",
            "votes": "999990000000"
        },
        {
            "publicKey": "03b12f99375c3b0e4f5f5c7ea74e723f0b84a6f169b47d9105ed2a179f30c82df2",
            "votes": "999720400000"
        },
        {
            "publicKey": "0346e1a1b5cb0720e863e8cf8a91dc8ed827e09fb4a4812f9f4d51f606e5359516",
            "votes": "999300000000"
        },
        {
            "publicKey": "02677f73453da6073f5cf76db8f65fabc1a3b7aadc7b06027e0df709f14e097790",
            "votes": "999200000000"
        },
        {
            "publicKey": "022e13de675e14a409ce636706c76d42857c673d8dc0dda4e5bfceffdbf86e13c9",
            "votes": "998880000000"
        },
        {
            "publicKey": "021b0f58eca7f123428a8647ffe0644a9454c510f066d3864c27d8c7ad8f5a8aa4",
            "votes": "998260000000"
        },
        {
            "publicKey": "02637b15aa50fa95018609a6d7b52b025de807a41b79b164626cee87dd6f61a662",
            "votes": "997080000000"
        },
        {
            "publicKey": "02ac8d84d81648154f79ba64fbf64cd6ee60f385b2aa52e8eb72bc1374bf55a68c",
            "votes": "996290000000"
        },
        {
            "publicKey": "03f89a2f86fe683dbbe4856a43c4c326fb2938ae2647fd334ad33261c7c2dee265",
            "votes": "996150000000"
        },
        {
            "publicKey": "027710de44279aaa41f8e75d5ae61a085020c414db2dbea02bbec0e0b1f27bcd22",
            "votes": "995930000000"
        },
        {
            "publicKey": "03f08761f99892996c6771761955ec41ee6cdffadd43171228f5f28f8c76423b3d",
            "votes": "994220000000"
        },
        {
            "publicKey": "026a423b3323de175dd82788c7eab57850c6a37ea6a470308ebadd7007baf8ceb3",
            "votes": "994170000000"
        },
        {
            "publicKey": "0335238d54c6ee73d79769d4ed43888d9b18e38c3594e656bb5a5544649d4f5ffe",
            "votes": "994140000000"
        },
        {
            "publicKey": "029a20963b506afabb2bd805830a46cef8d59218cd88c0dca9d2a0158045b1c3e0",
            "votes": "993890000000"
        },
        {
            "publicKey": "0349e7e2afb470994a8323e9623a6dab227c69d5f09f1a59991fd92880123ffe75",
            "votes": "993260000000"
        },
        {
            "publicKey": "03b906102928cf97c6ddeb59cefb0e1e02105a22ab1acc3b4906214a16d494db0a",
            "votes": "992940000000"
        },
        {
            "publicKey": "022eedf9f1cdae0cfaae635fe415b6a8f1912bc89bc3880ec41135d62cbbebd3d3",
            "votes": "992407676000"
        },
        {
            "publicKey": "0335fec08c867b80e3b71545be195e1b9876b2040d5393fc177b6edca78bde8e42",
            "votes": "991620000000"
        },
        {
            "publicKey": "03153c994e5306b2fbba9bb533f22871e12e4c1d1d3960d1eeef385ab143b258b4",
            "votes": "991440000000"
        },
        {
            "publicKey": "03f3512aa9717b2ca83d371ed3bb2d3ff922969f3ceef92f65c060afa2bc2244fb",
            "votes": "991240000000"
        },
        {
            "publicKey": "03c57b6a3eb7d01ade51f95c8ae4e8ebeb7ca7b8422ab0fb2a236de5d1a5bc6a1b",
            "votes": "991120000000"
        },
        {
            "publicKey": "03ef692bb144c368b4844ceca3ffd30fb8c82b97b5b40220473e9009925637e9f9",
            "votes": "990550000000"
        },
        {
            "publicKey": "02ff842d25fc8eec9e1382e6468188b3fd130ab6246240fc97958ce83d6d147eaf",
            "votes": "990140000000"
        },
        {
            "publicKey": "03508436f55577f406be58a5e7e59307cea823943c5312d62f4e3f3c63966f6e7c",
            "votes": "989640000000"
        },
        {
            "publicKey": "02257c58004e5ae23716d1c44beea0cca7f5b522a692df367bae9015a4f15c1670",
            "votes": "989460000000"
        },
        {
            "publicKey": "027b320c5429334ecf846122492d12b898a756bf1347aa61f7bf1dcd706315a9fb",
            "votes": "987310000000"
        },
        {
            "publicKey": "028dc808bd35583b28c6b12e09e6ae1e1dddd36a0bff4e5467d95d920b3caa4867",
            "votes": "623881000000"
        },
        {
            "publicKey": "0304d0c477d634cc85d89c1a4afee8f51168d1747fe8fd79cabc26565e49eb8a7a",
            "votes": "592380000000"
        },
        {
            "publicKey": "032e2dc53b703a1fc9763008c5cfbdf1eb7b2e52ce4c0998b790b5d08430e3720a",
            "votes": "562220000000"
        }
    ]
}
```

