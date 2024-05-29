# hash-data

This repo is used to host data blobs.

Use `cat thefile | shasum -a 256 | head -c20` to get the hash. 20 nibbles
(10 bytes) are used because this is enough to avoid a likely collision until
about a trillion entries. That's not cryptographically secure, but it doesn't
need to be.

Once you have the hash, create a branch with that name, and put a single file
there called `preimage`.
