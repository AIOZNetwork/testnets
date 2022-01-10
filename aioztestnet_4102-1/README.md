# aioztestnet_4102-1

- Seeds:

```
bb9747662642fa04268a64b82a7e29bd59949101@20.80.74.116:26656
```

## GenTx Generation

1. Initialize the gaia directories and create the local genesis file with the correct
   chain-id

   ```shell
   $ aiozd init monikername --chain-id=aioztestnet_4102-1
   ```

2. Create a local key pair in the Keybase

   ```shell
   $ aiozd keys add <key-name>
   ```

3. Add your account to your local genesis file with a given amount and the key you
   just created.

   ```shell
   $ aiozd add-genesis-account $(aiozd keys show <key-name> -a) 1000000000aioz
   ```

4. Create the gentx

   ```shell
   $ aiozd gentx --amount 100000000aioz \
     --commission-rate=<rate> \
     --commission-max-rate=<max-rate> \
     --commission-max-change-rate=<max-change-rate-rate> \
     --pubkey $(aiozd tendermint show-validator) \
     --name=<key-name>
   ```
