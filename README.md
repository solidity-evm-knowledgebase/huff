# huff

## Install Huff

```bash
curl -L get.huff.sh | bash
```
Then

```bash
huffup
```
Check that it was installed correctly:

```bash
huffc --version
```

## Compile a Contract with Huffc

```bash
huffc {PATH_TO_HUFF_CONTRACT}
```

adding -b will return the bytecode of the contract

```bash
huffc {PATH_TO_HUFF_CONTRACT} -b
```

Example output for simplest contract: `60008060093d393df3`

