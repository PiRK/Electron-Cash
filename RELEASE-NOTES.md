Electrum ABC is a fork of the open source Electron Cash wallet
(www.electroncash.org) for BCHA. The first release is based on the
Electron Cash 4.2.0 codebase with the following changes

- updated list of electrum servers
- updated icons and branding
- use different directory for wallets and configuration
- automatically import wallets and some configuration files from Electron Cash

The Electrum ABC software is NOT affiliated, associated, or endorsed by
Electron Cash, electroncahs.org or the Electrum developers.


# Usage

When you first run Electrum ABC it will use a different configuration
directory to Electron Cash. On Unix it is ".electrum-abc", and on Windows/MacOS
it is "ElectronCash".  Your wallet files will be copied from the Electrum
configuration directory (".electrum" on unix, "ElectrumABC" on Windows/MacOS),
if found.  Initially transactions will show up as unverified because
Electrum ABC is downloading the blockchain headers to verify the transactions.
This can take up to 10 minutes, but is only done once.

Ensure you are running Electrum ABC and not Electron Cash by checking for
"ElectrumABC" in the title bar wording.

We STRONGLY recommend you get comfortable and only send a small amount of BCHA
coins at first, to yourself, to confirm the network is processing your
transactions as expected.

After the recent network fork, it can take time for the Electrum server network
to split into two separate networks.  You should ensure you are connected to a
BCHA Electrum server in order to send transactions successfully. For this,
it is recommended that you leave the option "Connect only to preferred servers"
checked in the "Tools -> Network -> Server" menu.

In the future, there will be more servers available and there will no longer
be a risk to connect to the wrong network.


# Miscellaneous

BCHA is a cryptocurrency that was created during the recent Bitcoin Cash chain
split. When a chain split happens, one chain will typically hold onto the
original cryptocurrency name and ticker, while the other chain will become
a separate cryptocurrency with new branding. In this case, BCHN held on to
the BCH name and ticker.

That means BCHA will soon be branded with an official coin name, logo, and
ticker. After it launches, there will likely be a new release of Electrum ABC
with a new name.

In the meantime you can find out more about BCHA here:
https://bitcoinabc.org/bcha/

# Release notes

## Release 4.3.1

- Fixed a bug happening when clicking on a server in the network overview
  dialog.
- Enable the fiat display again, using CoinGecko's price for BCHA.
- Add a checkpoint to ensure only BCHA servers can be used. When splitting
  coins, it is now recommended to run both Electrum ABC and Electron Cash.
- Improve the automatic importing of wallets and user settings from
  Electron Cash, for new users: clear fiat historic exchange rates to avoid
  displaying BCH prices for pre-fork transactions, clear the server blacklist
  and whitelist, copy also testnet wallets and settings.
- When creating a new wallet, always save the file in the standard user
  directory. Previously, wallets were saved in the same directory as the
  most recently opened wallet.
- Change the crash report window to redirect users to github in their
  web browser, with a pre-filled issue ready to be submitted.
- Fix a bug when attempting to interact with a Trezor T hardware wallet
  with the autolock feature enabled, when the device is locked.


## Release 4.3.2

- Decrease the default transaction fee from 80 satoshis/byte to 10 sats/byte
- Add an option in the 'Pay to' context menu to scan the current screen
  for a QR code.
- Add a documentation page [Contributing to Electrum ABC](CONTRIBUTING.md).
- Remove the deprecated CashShuffle plugin.
- Fix a bug introduced in 4.3.1 when starting the program from the source
  package when the `secp256k1` library is not available. This bug did not
  affect the released binary files.
- Fix a bug related to the initial automatic copy of wallets from the
  Electron Cash data directory on Windows. The configuration paths were not
  changed accordingly, causing new wallets to be automatically saved in the
  Electron Cash directory.