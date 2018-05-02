### What's going on in `Mystery.sol`?

##### Answer:
The fallback function in Mystery.sol loads the addr from its storage. This address could
be a contract or account address. The fallback function, then calls that address with the same
calldata used to invoke that fallback function, essentially fowarding the call to the add in storage
with the gas used in the original tx. If the forwarded call reverts, so will the fallback function.
If it returns successfully, it will return whatever word is in the original 0x40 memory slot
