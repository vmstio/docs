# Translation

In order for Mastodon to offer to translate a post into a different language:

- The author of the post must have marked the language
- The language of the post must be different than your language
- The translation engine must be able to process the given combonation.

_ex: If a user posts content in Dutch, but the post is marked as being in English and your user interface is set to English, the Mastodon interface will not offer to translate the post._

Translation is done per-post only on-request by a user, as it would be computationally expensive to translate all posts that the server sees.

![Screenshot of Translate Button in Mastodon Interface](/translate.png)

The our translation API is also available to other client applications you may download to your devices.
These clients may also offer additional translation services which are outside of our control; for example, Ivory will use Apple's on-device translation API first, but then use the server's API if an unsupported language is detected.

Third party web clients like [Elk](https://elk.zone) and [Phanpy](https://phanpy.social) use different translation engines (LibreTranslate and Lingva) and may return different results.

