## Availup
To run an Avail light client, simply run the following command:
```bash
curl -sL1 avail.sh | bash
```
or, with `wget`:
```bash
wget --https-only --secure-protocol=TLSv1_2 --quiet -O - avail.sh | bash
```
You can pass additional flags to the script like:
```bash
curl -sL1 avail.sh | bash -s -- --network goldberg
```
Currently available flags are:
* `network`: can be one of the following: [`goldberg`, `local`]
* `config`: path to the configuration file, availup will generate a config if this flag is not specified
* `identity`: path to the identity file, availup will generate a config if this flag is not specified
* `app_id`: application ID to run the light client (defaults to `0`)
* `upgrade`: takes `y` and `yes` as valid arguments, indicating that the `avail-light` binary should be upgraded

You can modify the existing default config by running and rerun `availup` to use the new config:
```bash
# create the config:
touch ~/.avail/config/config.yml
# edit the config:
nano ~/.avail/config/config.yml
# and rerunning the script:
curl -sL1 avail.sh | bash -s -- --config ~/.avail/config/config.yml
```

Alternatively, you can pass a specific application ID with `availup`:
```bash
rm ~/.avail/goldberg/config.yml
# and rerunning the script with flags:
curl -sL1 avail.sh | bash -s -- --app_id 1
```

To upgrade the light client to a latest version, you can simply pass the `--upgrade` flag like:
```bash
curl -sL1 avail.sh | bash -s -- --upgrade y
```
