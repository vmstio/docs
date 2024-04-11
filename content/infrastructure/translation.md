---
title: Translation
---

# Translation

In order for Mastodon to offer to translate a post into a different language, **the post must be marked in that language** and it must be in a language that is possible for the translation engine to process.

_ex: If a user posts content in Dutch, but the post is marked as being in English and your user interface is set to English, the Mastodon interface will not offer to translate the post._

Translation is only done on-request by the user, as it would be computationally expensive to translate all posts that the server sees, as they are received or displayed.

## Client Engines

All of our hosted clients including the main Mastodon web interface, [Elk](/clients/elk) and [Phanpy](/clients/phanpy), support translation of user posts.
The main web interface API is also available to other client applications you may download to your devices, like Ivory, Mona, Tusky, etc.

### DeepL Pro

[DeepL](https://www.deepl.com/whydeepl) is used as the translation API for our main web interface and client API.

DeepL is free for limited use, but we pay for the professional plan which has additional data security standards that delete requests from their servers after they are translated.

### LibreTranslate

[LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) is used as translation API for our Elk web client interfaces.

LibreTranslate is a free and open source machine translation API.
Unlike other APIs, it doesn't rely on proprietary providers such as Google or Azure to perform translations.
Instead, its translation engine is powered by the open source Argos Translate library.

We use a LibreTranslate service hosted at [translate.mstdn.social](https://translate.mstdn.social).

### Lingva Translate

[Lingva Translate](https://github.com/thedaviddelta/lingva-translate) is used by our Phanpy client offering.

Lingva is an alternative front-end for Google Translate API, serving as a free and open source translator with over a hundred languages available.

## Available Languages

Support for translation by each engine may vary between engines and languages.
Each engine has languages that it is more accurate at translating, so even when translating the same post between each engine you may see different results.

| Language | [DeepL](https://support.deepl.com/hc/en-us/articles/360019925219-Languages-included-in-DeepL-Pro) | [LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) | [Lingva](https://en.wikipedia.org/wiki/Google_Translate#Supported_languages) |
|-----------------------|-----------------------------------------|-----------------------------------------|-------------------------------------------|
| Arabic                | :icon{name="twemoji:cross-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Azerbaijani           | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Bulgarian             | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Catalan               | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Chinese               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Czech                 | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Danish                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Dutch                 | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| English               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Esperanto             | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Estonian              | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Finnish               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| French                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| German                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Greek                 | :icon{name="twemoji:cross-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Hebrew                | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Hindi                 | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Hungarian             | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Indonesian            | :icon{name="twemoji:cross-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Irish                 | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Italian               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Japanese              | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Korean                | :icon{name="twemoji:cross-mark-button"} | :icon{name="twemoji:cross-mark-button"} | :icon{name="twemoji:cross-mark-button"}   |
| Latvian               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Lithuanian            | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Norwegian             | :icon{name="twemoji:cross-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Persian               | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Polish                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Portuguese            | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Romanian              | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Russian               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Slovak                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Slovenian             | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Spanish               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Swedish               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Turkish               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Ukrainian             | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |

_Lingva Translate may support additional languages not listed here._