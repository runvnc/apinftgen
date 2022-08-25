# NFTGEN API v1

The creator can create an API Key on the API tab.

## Base URL and API Key

Base url for all calls is `https://algonfts.art/v1/`.
The API key is specified in the `NFTGEN-KEY` header.

## Generate

`/generate/[COLLECTION ADDRESS]` (optional traits in query string)

Generate an image using the collection image assets and configuration, returning image URL and Arc69/Arc19 metadata.

### Examples

Generate an image with random traits:

`curl "https://algonfts.art/v1/generate1/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA" -H "NFTGEN-KEY: GWQHTJA-5FNECQY-RTZZSTY-MFLEXTA`

Generate an image with a blue background and random foreground:

`curl "https://algonfts.art/v1/generate1/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA?bg=blue" -H "NFTGEN-KEY: GWQHTJA-5FNECQY-RTZZSTY-MFLEXTA`

Generate an image with a blue background and orange foreground:

`curl "https://algonfts.art/v1/generate1/SGNMPHKQAJUG3DTJSGO6HHWP55CVSY6DD4CITFGD7QLFRTHHC237TGTRUA?bg=blue" -H "NFTGEN-KEY: GWQHTJA-5FNECQY-RTZZSTY-MFLEXTA`

## Credits

There will be a credits system (probably purchased with ALGOs) with an inexpensive charge for each item. Test mode images probably around $0.01 USD equivalent, full size images $0.1 USD equivalent. Pricing not finalized.

## Plans

Tentatively planned: 

* `/pin` (pin on both Filebase and web3.storage)

* `test` mode images (smaller with watermark)

* `/traits` (get list of traits and variants)

* TypeScript SDK with `generate() and `pin()`, plus possibly something like `getCreateTxn/getReconfigTxn`,
  maybe `create/reconfig` (given account and properties, do generate, pin and asset config)


