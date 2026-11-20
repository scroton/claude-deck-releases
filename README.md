# Claude Deck - signed releases

Only the release files of Claude Deck's native app live here (the exe, the install zip), each signed with Mike's
office release key. The source is not here.

## Check a download before you run it

The key is [`KEYS`](KEYS) here and at https://github.com/scroton.gpg:

    scroton (office release signing) <michael.stoyer@gmail.com>
    fingerprint 5C55 F4E8 FABD CCD5 1CA0  3CF4 2693 D3CD ACEA 3664

With `gpg` (Git for Windows ships it), in the folder holding the downloaded files:

```bash
gpg --import KEYS
gpg --verify SHA256SUMS.asc SHA256SUMS
sha256sum -c SHA256SUMS --ignore-missing
```

Good = `Good signature from "scroton (office release signing)"` with the fingerprint above, and `OK` for every file.
Anything else: do not run it, and tell Mike.

The app updates itself from here: it downloads a newer release only when `SHA256SUMS.asc` verifies against this key
and the exe's hash is in `SHA256SUMS`.
