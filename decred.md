# Decred

* [https://dcrstats.com/](https://dcrstats.com/)
* [https://mainnet.decred.org](https://mainnet.decred.org)
* [https://stats.decred.org/](https://stats.decred.org/)

  **Ticketsplitting**

* [https://github.com/matheusd/dcr-split-ticket-matcher/blob/master/docs/building.md](https://github.com/matheusd/dcr-split-ticket-matcher/blob/master/docs/building.md)
* [https://github.com/matheusd/dcr-split-ticket-matcher/blob/master/docs/client-cli.md](https://github.com/matheusd/dcr-split-ticket-matcher/blob/master/docs/client-cli.md)
* [https://mainnet-split-tickets.matheusd.com/](https://mainnet-split-tickets.matheusd.com/)
  * Lists ongoing ticketsplitting sessions that you can join
* [https://slack.decred.org/](https://slack.decred.org/)
  * Discuss and coordinate ticketsplitting on the \#ticket\_splitting channel

### Building The Splitter

```text
go build ./cmd/...
bin/build-buyer-linux.sh
```

### Using The Splitter

taken from a user guide posted to the Decred Slack:

The following instructions are for users of Decrediton and will walk you through getting setup for ticket splitting. To participate in ticket splitting, you must have:

• A user account on on of the supported pools: DECREDVOTING.COM STAKE.DECREDBRASIL.COM • v0.6.2 of matheusd's ticket splitting software. • At least 5.0 DCR

To get started, follow these steps:

1. Create an account with one of the pools and follow the account setup instructions for that pool.
2. Download and extract the ticket splitting utility for your OS: • Windows 64-bit • Linux 64-bit • Mac

3a. Run Decrediton and load your wallet. Make sure that Decrediton has sync'd to the latest block. 3b. Run splitticketbuyergui from the package you just downloaded.

1. Click the Config menu item in splitticketbuyergui and select "Load from Decrediton". Verify that the Vote Address and Pool Subsidy Address fields have populated as follows: • The vote address should begin with Dc and the Pool Subsidy Address should begin with Ds. • Also, verify that the Matcher Host shows the matcher from your selected pool. • Note: If you are running Ubuntu, you may need to specify the port number with the matcher host in the configuration file. Such a configuration would look like: `<matchername>:8475`
2. Adjust the slider at the top of Split Ticket Buyer to the amount of DCR that you want to contribute to the ticket. Please note that the minimum you can participate with is 5 DCR! Also, note that the splittickerbuyer GUI will only let you contribute an integer. It is possible to contribute down to the hundredth's place by using the CLI version of split-ticket-buyer.
3. Create a test session to make sure things work. \(Make sure Decrediton is running and your wallet is loaded!\) Note: To ensure that a ticket is not unintentionally funded, choose a random string of letters & numbers to use as the session name for this test. If you happen to enter the same session name as another user and there is enough combined DCR in the session to fully fund a ticket, the transaction will go through and both you and the other user will have purchased a split ticket. If you do not see any sessions in the Currently Waiting Sessions list at the bottom of this page then there are no open sessions and the risk is minimal. a. Enter a random Session Name b. Enter your wallet passphrase c. Click on Participate. Read and accept the disclaimer. d. The text window in the split ticket buyer should show: "Waiting participants \(\# DCR\): \[\# DCR\]" and your session should appear on this page below in the Currently Waiting Sessions section.

Congratulations! You are now setup for ticket splitting!

To split a ticket, Decrediton must remain open with your wallet loaded. Establish a partner to split a ticket with in the \#ticket\_splitting channel on Decred Slack or or here in the Telegram group. Help is available on both platforms with setting up ticket splitting as well.

Note: The ticket splitting service will reject any sessions when the ticket price is +/- 5 blocks away from changing. Also, it is strongly recommended that you keep Decrediton open until the ticket purchase transaction changes from pending to confirmed.

### Decred Brasil

* [https://stake.decredbrasil.com/docs](https://stake.decredbrasil.com/docs)

if you are a Linux user and you have the Decred Brasil stakepool set up in Decrediton, launch the ticket splitter with `./splitticketbuyergui --matcher.host split-ticket-svc.stake.decredbrasil.com:8475` and you will be victorious

config, load from decrediton, participate and that should do it for you

### decredvoting.com

[https://decredvoting.com/ticketsplitting](https://decredvoting.com/ticketsplitting)

`dcr-split-ticket-matcher/dist/release/linux-x86_64/split-ticket-buyer$ ./splitticketbuyergui --matcher.host matcher.decredvoting.com:8475 --maxtime 36000`

