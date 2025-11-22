# Global Username/Name Search Bookmarklet

This repository hosts a powerful JavaScript bookmarklet designed to perform a simultaneous, highly-targeted search for a specific name or username across multiple major social media platforms and public sites, utilizing the power of multiple search engines.

It's a quick, one-click tool perfect for OSINT, digital footprint analysis, or simply verifying a user's presence across the web.

##  Features

  * **Multi-Engine Search:** Simultaneously opens new tabs for Google, DuckDuckGo, and Yandex.
  * **Targeted Site Inclusion:** Automatically includes a long list of `site:` operators (e.g., LinkedIn, Twitter, Instagram, Reddit, TikTok) to focus the search results.
  * **Quote Wrapping:** Encloses the entered name/username in quotes (`" "`) to ensure an exact-match search.
  * **Easy Installation:** Installable in any major browser in seconds.

##  Installation

### 1\. Copy the Code

Copy the entire minified code block below:

```javascript
javascript:(function(){const name=prompt("Enter the name or username you want to search across ALL platforms (e.g., Jane Doe, @jdoe):");if(name){const query=`"${name}" (site:linkedin.com | site:facebook.com | site:twitter.com | site:instagram.com | site:reddit.com | site:pinterest.com | site:tiktok.com | site:youtube.com | site:cash.app | site:snapchat.com | site:bandlab.com | site:bsky.app | site:poshmark.com | site:threads.net | site:smule.com | site:t.me | site:soundcloud.com)`;const encodedQuery=encodeURIComponent(query);const googleUrl=`https://www.google.com/search?q=${encodedQuery}`;const duckduckgoUrl=`https://duckduckgo.com/?q=${encodedQuery}`;const yandexUrl=`https://yandex.com/search/?text=${encodedQuery}`;window.open(googleUrl,'_blank');window.open(duckduckgoUrl,'_blank');window.open(yandexUrl,'_blank');}})();
```

### 2\. Create the Bookmark

1.  **Open your browser's Bookmark Manager** (usually by pressing **Ctrl+Shift+O** or **Cmd+Option+B**).
2.  **Add a new bookmark.**
3.  Set the **Name** (Title) to something descriptive, like `OSINT Global Search`.
4.  In the **URL** (Address) field, **paste the code** copied in Step 1.
5.  Save the bookmark. It is recommended to place it on your bookmarks bar for one-click access.

##  How to Use

1.  Navigate to any webpage (it doesn't matter which one).
2.  Click the new `OSINT Global Search` bookmarklet.
3.  A prompt box will appear. Enter the exact **Name** or **Username** you wish to search for (e.g., `elonmusk` or `Jane Doe`).
4.  Four new tabs will automatically open, executing the search on Google, DuckDuckGo, and Yandex.

##  How the Search Query Works

The bookmarklet constructs a highly optimized search query using Google Dorks/Search Operators:

1.  The name/username is wrapped in quotes: `"Jane Doe"`. This forces the search engine to look for that exact phrase.
2.  The query appends a long list of platforms using the **OR** operator (`|`) and the **site** operator (`site:`):
    ```
    (site:linkedin.com | site:facebook.com | site:twitter.com | ... | site:youtube.com)
    ```
3.  The final resulting search string looks like this:
    ```
    "Jane Doe" (site:linkedin.com | site:facebook.com | site:twitter.com | site:instagram.com | site:reddit.com | site:pinterest.com | site:tiktok.com | site:youtube.com | site:cash.app | site:snapchat.com | site:bandlab.com | site:bsky.app | site:poshmark.com | site:threads.net | site:smule.com | site:t.me | site:soundcloud.com)
    ```

This technique drastically improves the accuracy and relevance of the results by instructing the search engines to only show pages from those specific domains that contain the exact phrase you entered.

## 🔗 Targeted Platforms

The following platforms are included in the search query using the `site:` operator to maximize relevant results across all search engines:

| Category | Platform(s) |
| :--- | :--- |
| **Professional** | `site:linkedin.com` |
| **Major Social** | `site:facebook.com`, `site:instagram.com`, `site:twitter.com` (X), `site:tiktok.com`, `site:youtube.com`, `site:threads.net`, `site:snapchat.com` |
| **Communities** | `site:reddit.com` |
| **Media/Sharing** | `site:pinterest.com`, `site:soundcloud.com`, `site:bandlab.com`, `site:smule.com` |
| **Messaging** | `site:t.me` (Telegram) |
| **Alt/Decentralized**| `site:bsky.app` (Bluesky) |
| **Finance/Retail** | `site:cash.app`, `site:poshmark.com` |

##  Contributing

Feel free to suggest additions to the list of sites or propose other useful OSINT bookmarklets\!

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/new-sites`).
3.  Update the `query` string in the source code.
4.  Create a Pull Request.

