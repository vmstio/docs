# Translation

In order for Mastodon to offer to translate a post into a different language, the post must be marked in that language and it must be in a language that is possible for the translation engine to process.

_ex: If a user posts content in Dutch, but the post is marked as being in English and your user interface is set to English, the Mastodon interface will not offer to translate the post._

Translation is only done on-request by the user, as it would be computationally expensive to translate all posts that the server sees, as they are received or displayed.

![Screenshot of Translate Button in Mastodon Interface](/translate.png)

## Client Engines

The main Mastodon web interface, as well as hosted solutions like [Elk](https://elk.zone) and [Phanpy](https://phanpy.social), support translation of user posts.

| Client | DeepL | LibreTranslate | Lingva |
|--------|-------|----------------|--------|
| Mastodon (API)    | :icon{name="twemoji:check-mark-button"}   | :icon{name="twemoji:white-circle"}        | :icon{name="twemoji:cross-mark"}          |
| Elk               | :icon{name="twemoji:cross-mark"}          | :icon{name="twemoji:check-mark-button"}   | :icon{name="twemoji:cross-mark"}          |
| Phanpy            | :icon{name="twemoji:cross-mark"}          | :icon{name="twemoji:cross-mark"}          | :icon{name="twemoji:check-mark-button"}   |

The main web interface API is also available to other client applications you may download to your devices, like Ivory, Mona, Tusky, etc.
These clients may also offer additional translation services which are outside of our control; for example, Ivory will use Apple's translation API first, but then use our API if it is unavailable or an unsupported language is detected.

### DeepL

[DeepL](https://www.deepl.com/whydeepl) is used as the translation API for our main web interface and client API.
It is known for its accuracy and ability to grasp nuances in language better than many other translation services.

DeepL is free for limited use, but we pay for the professional plan which has additional data security standards that delete requests from their servers after they are translated.

### LibreTranslate

[LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) is used as the translation API for the Elk web client interfaces.

LibreTranslate is a free and open-source machine translation API.
Unlike other APIs, it doesn't rely on proprietary providers.
The translation engine is powered by the open-source Argos Translate library.

### Lingva

[Lingva](https://github.com/thedaviddelta/lingva-translate) is used by the Phanpy client offering.

Lingva is an alternative front-end for Google Translate API, serving as a free and open-source translator with over a hundred languages available.
While it has the widest set of available languages it can process, it is reliant on a third-party service, which then sends data to Google.
