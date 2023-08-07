# Subreddit Redirect Shortcut Firefox Extension

## Overview

This is a Firefox extension that automatically redirects your searches for specific subreddits to the corresponding subreddit page on Reddit. It works with various search engines that use the `q` or `p` parameter for the searched text. The extension detects if the search query matches a Reddit subreddit pattern and instantly redirects the user to the relevant subreddit on Reddit.

## Tested Search Engines

The extension has been tested and confirmed to work with the following search engines:

- google.com
- duckduckgo.com
- bing.com
- yahoo.com
- aol.com

## How It Works

The extension listens for navigation events using the `browser.webNavigation.onBeforeNavigate` API. When the user initiates a search, the extension intercepts the URL of the search result page and extracts the search query from the URL parameters.

The extension looks for two possible URL parameters:

1. `q`: This is the common parameter used by search engines like Google, Bing, DuckDuckGo, and AOL.
2. `p`: Yahoo uses this parameter for searches.

If the extension detects that the URL is not related to Reddit or that neither the `q` nor the `p` parameter matches a specific subreddit pattern, it does nothing, allowing the user to continue browsing normally.

However, if the search query matches a Reddit subreddit pattern, the extension takes the subreddit name (removing the leading "r/") and constructs a new URL for the corresponding subreddit on Reddit.

The user's tab is then updated with the new Reddit URL, automatically redirecting them to the desired subreddit.

## Compatibility

The extension should work with most search engines that follow the standard `q` or `p` parameter convention for search queries. It is designed to be lightweight and efficient, ensuring a seamless browsing experience for the user.

## Installation

To install the extension, follow these steps:

1. Clone the repository with `git clone https://github.com/mirolaukka/subreddit-shortcut-firefox.git`.
2. Open Firefox and navigate to `about:addons`.
3. Click on the cog wheel icon below the search bar.
4. Click on the "Install Add-on From File..." button and select the `.xpi` file inside `./web-ext-artifacts` from inside the directory you cloned.
5. The extension will be installed, and you should see its icon added to your extensions list.

## Feedback and Bug Reporting

We welcome any feedback or bug reports related to this extension. If you encounter any issues or have suggestions for improvement, please feel free to create an issue on the GitHub repository.

## Disclaimer

This extension is provided as-is, and the developer assumes no responsibility for any data loss, security breaches, or other issues that may arise from its usage. Please use the extension responsibly and make sure to review the code to understand its functionalities before installation.

Happy browsing!