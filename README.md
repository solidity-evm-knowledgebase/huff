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

To get only the runtime contract code:

```bash
huffc {PATH_TO_HUFF_CONTRACT} --bin-runtime
```

Example output for simplest contract: `60008060093d393df3`

## Macro

Macro are "functions" in Huff. Example:

```huff
#define macro MAIN() = takes(0) returns(0) {}
```

## Function Selector

We can define our functions at the top of the contract, and Huff will take care of converting it to the function selector. 
Example:

```huff
/* Interfaces */
#define function updateHorseNumber(uint256) nonpayable returns()
#define function readNumberOfHorses() view returns(uint256)
```

We can then use them like this:

```huff
__FUNC_SIG(updateHorseNumber)
```

## Storage

Huff abstracts keeping track of storage variables through the FREE_STORAGE_POINTER() keyword.

```huff
#define constant STORAGE_SLOT0 = FREE_STORAGE_POINTER()
#define constant STORAGE_SLOT1 = FREE_STORAGE_POINTER()
#define constant STORAGE_SLOT2 = FREE_STORAGE_POINTER()
```


