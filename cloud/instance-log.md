# SCS2b.3 Instance Log -- fisher

## 1. Key Pair Generation
- **Typed:** `ssh-keygen -t ed25519 -f ~/.ssh/fisher-key -N "" && chmod 600 ~/.ssh/fisher-key`
- **Expected:** Ed25519 key pair generated in `~/.ssh/` with private key mode 600.
- **Seen:** `fisher-key` and `fisher-key.pub` generated (`SHA256:QWdWZDf7cSi7F4Wl1Ha5oKoIIG+BfeMhaNcEKQlrHOY`); public key ready for AWS import.
