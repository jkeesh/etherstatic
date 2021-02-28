# Etherstatic

Host static webpages in ethereum transactions.

The Etherstatic project lets you host static websites, or any arbitrary text
within the ethereum blockchain.

This tool makes it very simple to publish your webpage to the blockchain in an
ethereum-enabled browser, and specifically gives instructions for setting up
metamask.

View the website here: http://etherstatic.com

After you publish your static webpage or text through etherstatic, it will be hosted
on the ethereum blockchain for as long as it exists. It can be used to provide a
record of something. While you might pay a recurring cost for your own web hosting server,
you just pay a one time cost to the ethereum network and then it is published there.

### Sample Webpage

View a webpage hosted within the ethereum blockchain http://etherstatic.com/t#0xd2426eaa74bc162f2738295f58376f46ca9dd6705f450ff5dc805e4632fd7826

This webpage is being read from the ethereum blockchain at this transaction: https://etherscan.io/tx/0xd2426eaa74bc162f2738295f58376f46ca9dd6705f450ff5dc805e4632fd7826

### How it works

You can publish any html or text as data in an ethereum transaction, and this
site provides an interface to publish the site, or view an existing transaction
as a website.

The html or ascii data is converted to hex and then published as the data in a
transaction. The value sent is 0, so the total cost paid is the cost of the gas
associated with the size of the data.

### How to run

- Clone the git repository
- Run `$ python -m http.server 8080`
    Updated for python3
- Visit in your browser at localhost:8080

## To deploy

- $ git push web master


### Links

This website is built using ethereum nodes from infura https://infura.io/

Listed on the State of the Dapps: https://dapps.ethercasts.com/


### Web3 Library

https://github.com/ChainSafe/web3.js?source=post_page-----e3fbe89111c3----------------------
