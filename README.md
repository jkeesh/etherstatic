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

### How to run locally

    python3 -m http.server 8080

Then visit http://localhost:8080/

### To deploy

    git push web master       # → live site (post-receive hook auto-deploys)
    git push origin master    # → GitHub mirror

### Remotes

- `origin` → `git@github.com:jkeesh/etherstatic.git`
- `web`    → `ssh://jkeesh@172.234.29.183/home/jkeesh/repos/etherstatic.git` (new Linode)

### Infrastructure

- **Ethereum reads:** the viewer at `/t/` uses a free public JSON-RPC endpoint
  (`https://ethereum-rpc.publicnode.com`) via native `fetch()`. No API key.
  Swap one line in `t/index.html` to a different endpoint if it goes down
  (llamarpc, blastapi, meowrpc, etc.).
- **Web3 library:** none — originally used web3.js, but web3@latest (v4) dropped
  the callback API the viewer relied on. Rewritten to just use `fetch()` and
  hex-decode the transaction `input` field directly. Smaller, simpler, faster.

### Listed on

State of the Dapps: https://dapps.ethercasts.com/
