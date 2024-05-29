# hash-data

This repo is used to host data blobs.

Use `cat thefile | shasum -a 256 | head -c20` to get the hash. 20 nibbles
(10 bytes) are used because this is enough to avoid a likely collision until
about a trillion entries. That's not cryptographically secure, but it doesn't
need to be.

Once you have the hash, create a branch with that name, and put a single file
there called `preimage`.

```
git checkout --orphan BRANCH_NAME
git reset --hard # careful you don't have any repo files lying around
# put your file here and call it preimage
git add preimage
git commit -m 'init'
git push -u origin HEAD
```

You can then access the data via github from this url:
`https://raw.githubusercontent.com/linkologer/hash-data/BRANCH_NAME/preimage`
