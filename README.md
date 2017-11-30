# NAME
   `setzer` -- manipulate feeds and update data

# SYNOPSIS
   `setzer <command> [<args>]`  
   `setzer <command> --help`

# INSTALLATION
   `make link`       install setzer(1) into /usr/local  
   `make uninstall`  uninstall setzer(1) from /usr/local
# SETUP
  setzer expects a `/etc/setzer.conf` file that looks like this:

```bash
  export ETH_FROM="YOUR ACCOUNT"
  export SETZER_FEED="YOUR PRICE-FEED ADDRESS"
  export SETZER_MEDIANIZER="0x729D19f657BD0614b4985Cf1D82531c67569197B"
  export SETZER_SOURCES="LIST OF PRICE SOURCES"
  
  #LIST OF RPC PORTS TO CONNECT TO
  export RPC_PORTS="8545"
  
  #TIME TO WAIT FOR A NODE TO RESPOND
  export RPC_TIMEOUT=5s
```
# DEPENDENCIES
   seth(1)         https://github.com/dapphub/seth  
   curl(1)         https://curl.haxx.se/  
   jshon(1)        https://github.com/mbrock/jshon/

# COMMANDS

  | command    |     description                                            |
  |------------|------------------------------------------------------------|
  |`average`   |      get average price of 2 or more price \<source>        |
  |`bot`       |      really cool bot                                       |
  |`compute`   |      get what the medianizer value would be if updated     |
  |`expires`   |      get expiration in seconds (< 0 means expired)         |
  |`help`      |      print help about setzer(1) or one of its subcommands  |
  |`peek`      |      peek a dsvalue, dscache or medianizer                 |
  |`poke`      |      poke a medianizer                                     |
  |`poker`     |      update a poker                                        |
  |`post`      |      update a ds-price                                     |
  |`price`     |      show ETH/USD price from \<source>                     |
  |`prod`      |      update a ds-cache                                     |
  |`read`      |      read a dsvalue, dscache or medianizer                 |
  |`set`       |      set next feed of a medianizer                         |
  |`spread`    |      variance of 2 values in %                             |
  |`valid`     |      check if a dsvalue, dscache or medianizer has a value |
  |`void`      |      invalidate a feed                                     |
  |`volume`    |      show ETH/USD volume from <source>                     |

# OPTIONS
   You can provide any `seth` option to commands that send transactions.  
   For example `setzer void <feed> -F <account> --gas=100000 -P 1000000000`

Report bugs to <https://github.com/makerdao/setzer/issues>.

Thanks to @dbrock for paving the way with `seth` and `dapp`