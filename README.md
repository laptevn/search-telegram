# Telegram Post Finder

Search public Telegram channel posts by keyword, scan short message previews, and open the original posts directly in Telegram.

Built for finding job opportunities across Telegram channels—for example, posts mentioning `Fullstack engineer`, `engineer`. You can also search for other topics.

**Made by Nick Laptev.**

## Features

- Two-step interface: authenticate, then search.
- Search through Telegram’s official MTProto API.
- Find public channel posts, including channels you haven’t joined.
- Short previews with matching text highlighted.
- Channel names, publication dates, and direct post links.
- Load additional results with pagination.
- Support for Telegram sign-in codes and two-step verification passwords.
- One self-contained HTML file with embedded JavaScript and styles.

## Quick start

1. Download `telegram-post-finder.html` from this repository.
2. Open the file in a modern browser. No installation or local server is required.
3. Enter your Telegram **API ID**, **API hash**, and **phone number**.
4. Enter the sign-in code Telegram sends you.
5. If prompted, enter your Telegram two-step verification password.
6. After signing in, enter a keyword such as `Fullstack engineer` and select **Search posts**.
7. Scan the previews and select **Open in Telegram** to read an original post.

Internet access is required to connect to Telegram. Signing out returns you to the authentication step.

### Get your API credentials

Open [my.telegram.org/apps](https://my.telegram.org/apps), sign in, and create an application under **API development tools**. Telegram will provide an API ID and API hash.

Each user should use their own credentials and Telegram account. A bot token cannot be used for this search.

### Two-step verification password

This is the additional account password configured in Telegram under **Settings → Privacy and Security → Two-Step Verification**. It is separate from your one-time sign-in code and the local passcode used to unlock the Telegram app.

If you forget it, use Telegram’s recovery options in the official app.

## Search scope and limits

The app uses [`channels.searchPosts`](https://core.telegram.org/method/channels.searchPosts) to search public channel posts. It does not search all Telegram chats or provide access to private conversations.

Results are matching posts, not automatically verified job descriptions. Use the preview and original post to check relevance.

Telegram controls search availability and account limits. Text search may require Telegram Premium. The app checks the free search allowance and stops when a payment would be required—it never authorizes a Telegram Stars payment.

Rate limits and temporary restrictions may also apply. If Telegram asks you to wait, retry later.

## Privacy

The app connects directly from your browser to Telegram. It has no application backend for collecting your credentials or results.

Credentials, the local session, and search results are held in page memory. The app does not save them to browser storage. Refreshing or closing the page clears that local state, so you will need to sign in again.

To revoke a Telegram session, use **Settings → Devices** in the official Telegram app.

Do not commit API credentials, passwords, sign-in codes, or session keys to the repository.

## Sharing

Share `telegram-post-finder.html` as a file. JavaScript and styles are embedded, so recipients do not need to install dependencies. They authenticate with their own Telegram accounts.

## License

The project’s original code is licensed under the [MIT License](LICENSE): free to use, modify, and redistribute, including commercially, subject to retaining the copyright and license notice.

Bundled third-party components remain subject to their respective licenses. Preserve their required copyright and license notices when redistributing the application.
