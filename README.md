# NFTGEN API v1

The creator can create an API Key on the API tab.

## Base URL and API Key

Base url for all calls is `https://algonfts.art/v1/`.
The API key is specified in the `NFTGEN-KEY` header.

## Generate

`/generate/[COLLECTION ADDRESS]` (optional traits in query string)

Generate an image using the collection image assets and configuration, returning image URL and Arc69/Arc19 metadata.

### Examples

Demo account is configured with two traits: a solid background color and a small solid color foreground square.

Generate an image with random traits:

```sh
curl "https://algonfts.art/v1/generate1/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA" \
     -H "NFTGEN-KEY: GWQHTJA-5FNECQY-RTZZSTY-MFLEXTA"
```

Result (formatted):

```json
{
    "filename": "1661449078005.webp",
    "cid": "bafkreiauz6nx4362y7howx5ujkja7d7vhxzjzx6ujmoj2b7fx65ye2aeye",
    "imageurl": "https://algonfts.art/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA/1/1661449078005.webp",
    "arc69": {
        "standard": "arc69",
        "mime_type": "image/webp",
        "media_url": "ipfs://bafkreiauz6nx4362y7howx5ujkja7d7vhxzjzx6ujmoj2b7fx65ye2aeye",
        "properties": {
            "bg": "red",
            "fg": "smallorange 1661449077944"
        }
    },
    "arc19": {
        "url": "template-ipfs://{ipfscid:1:raw:reserve:sha2-256}",
        "reserve": "CTHZW7TP3LD45227WRFJED4P6U67FHG72RFRZHIH4W73XATIATAZZBNCXM"
    }
}
```

Generate an image with a blue background and random foreground:

```sh
curl "https://algonfts.art/v1/generate1/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA?bg=blue" \
     -H "NFTGEN-KEY: GWQHTJA-5FNECQY-RTZZSTY-MFLEXTA"
```

Result (formatted):

```json
{
    "filename": "1661449078419.webp",
    "cid": "bafkreievpik2sutrb5fa4sg5zrhxeryzmnpd2emnfay2zyhqe6qcb4xs5q",
    "imageurl": "https://algonfts.art/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA/1/1661449078419.webp",
    "arc69": {
        "standard": "arc69",
        "mime_type": "image/webp",
        "media_url": "ipfs://bafkreievpik2sutrb5fa4sg5zrhxeryzmnpd2emnfay2zyhqe6qcb4xs5q",
        "properties": {
            "bg": "blue",
            "fg": "smallyellow 1661449078359"
        }
    },
    "arc19": {
        "url": "template-ipfs://{ipfscid:1:raw:reserve:sha2-256}",
        "reserve": "SV5BLKKSOEHUUDSI3XGE64SHDFRV4PIRRUUDDLHA6AT2AIHS6LWOZRPCRA"
    }
}
```

## Credits

There will be a credits system (probably purchased with ALGOs) with an inexpensive charge for each item. Test mode images probably around $0.01 USD equivalent, full size images $0.1 USD equivalent. Pricing not finalized.

## Plans

Tentatively planned: 

* `/pin` (pin on both Filebase and web3.storage)

* `test` mode images (smaller with watermark)

* `/traits` (get list of traits and variants)

* TypeScript SDK with `generate() and `pin()`, plus possibly something like `getCreateTxn/getReconfigTxn`,
  maybe `create/reconfig` (given account and properties, do generate, pin and asset config)


