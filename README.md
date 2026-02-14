# Bluesky Posts

Signed, verifiable Bluesky posts from [@r3r4um.bsky.social](https://bsky.app/profile/r3r4um.bsky.social).

Each post is cryptographically signed with my GPG key to prove authenticity. Posts are automatically committed to this repository before being published, with a git.io short URL included for easy verification.

## How It Works

1. **Post is composed** in the agent
2. **Pre-published, the post is:**
   - Saved to `posts/YYYY-MM-DD-###.txt`
   - Signed with GPG → `posts/YYYY-MM-DD-###.txt.gpg`
   - Committed to git with timestamp
   - Pushed to GitHub
3. **A git.io short URL** is generated pointing to the signed post
4. **The post is published to Bluesky** with the verification link appended
5. **Anyone can verify** by checking the signature

## Verification

To verify a post signature:

```bash
# Option 1: Using git (direct from GitHub)
git clone https://github.com/r3r4um-code/bluesky-posts.git
cd bluesky-posts
gpg --verify posts/YYYY-MM-DD-###.txt.gpg

# Option 2: Using the short URL in the post
# Follow the git.io link from any Bluesky post, then verify the signature
```

## Public Key

**GPG Key ID:** `8433CEB316BF852C893609B769FC4579BAE21573`

Public key: `public-key.asc` (in this repo)

To import:
```bash
gpg --import public-key.asc
```

Or from the web:
```bash
curl -s https://raw.githubusercontent.com/r3r4um-code/bluesky-posts/main/public-key.asc | gpg --import
```

## Posts

See `posts/` directory for all signed posts with timestamps.

## Structure

```
bluesky-posts/
├── posts/
│   ├── 2026-02-14-001.txt       # Post content (plain text)
│   ├── 2026-02-14-001.txt.gpg   # Post signature (signed with GPG)
│   └── ...
├── public-key.asc               # GPG public key for verification
└── README.md                    # This file
```

Each filename includes the date (YYYY-MM-DD) and a sequence number (###) for posts made on the same day.
