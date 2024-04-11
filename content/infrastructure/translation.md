---
title: Translation
---

# Translation

In order for Mastodon to offer to translate a post into a different language, **the post must be marked in that language** and it must be in a language that is possible for the translation engine to process.

_ex: If a user posts content in Dutch, but the post is marked as being in English and your user interface is set to English, the Mastodon interface will not offer to translate the post._

Translation is only done on-request by the user, as it would be computationally expensive to translate all posts that the server sees, as they are received or displayed.

![Screenshot of Translate Button in Mastodon Interface](/translate.png)

## Client Engines

All of our hosted clients including the main Mastodon web interface, [Elk](/clients/elk) and [Phanpy](/clients/phanpy), support translation of user posts.

| Client | DeepL | LibreTranslate | Lingva |
|--------|-------|----------------|--------|
| Mastodon (API)    | :icon{name="twemoji:check-mark-button"}   | :icon{name="twemoji:white-circle"}        | :icon{name="twemoji:cross-mark"}          |
| Elk               | :icon{name="twemoji:cross-mark"}          | :icon{name="twemoji:check-mark-button"}   | :icon{name="twemoji:cross-mark"}          |
| Phanpy            | :icon{name="twemoji:cross-mark"}          | :icon{name="twemoji:cross-mark"}          | :icon{name="twemoji:check-mark-button"}   |

The main web interface API is also available to other client applications you may download to your devices, like Ivory, Mona, Tusky, etc.
These clients may also offer additional translation services which are outside of our control, for example Ivory will fallback to Google Translate directly if our API is unavailable or an unsupported language is detected.

### DeepL

[DeepL](https://www.deepl.com/whydeepl) is used as the translation API for our main web interface and client API.

DeepL is free for limited use, but we pay for the professional plan which has additional data security standards that delete requests from their servers after they are translated.

### LibreTranslate

[LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) is used as translation API for our Elk web client interfaces.

LibreTranslate is a free and open source machine translation API.
Unlike other APIs, it doesn't rely on proprietary providers such as Google or Azure to perform translations.
Instead, its translation engine is powered by the open source Argos Translate library.

We use a LibreTranslate service hosted at [translate.mstdn.social](https://translate.mstdn.social).

### Lingva

[Lingva](https://github.com/thedaviddelta/lingva-translate) is used by our Phanpy client offering.

Lingva is an alternative front-end for Google Translate API, serving as a free and open source translator with over a hundred languages available.

## Available Languages

Support for translation by each engine may vary between engines and languages.

| Language | [DeepL](https://support.deepl.com/hc/en-us/articles/360019925219-Languages-included-in-DeepL-Pro) | [LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) | [Lingva](https://en.wikipedia.org/wiki/Google_Translate#Supported_languages) |
|-----------------------|-----------------------------------------|-----------------------------------------|-------------------------------------------|
| Arabic                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
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
| Greek                 | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Hebrew                | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Hindi                 | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Hungarian             | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Indonesian            | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Irish                 | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Italian               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Japanese              | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Korean                | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:check-mark-button"}   |
| Latvian               | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Lithuanian            | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
| Norwegian             | :icon{name="twemoji:check-mark-button"} | :icon{name="twemoji:cross-mark"}        | :icon{name="twemoji:check-mark-button"}   |
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

### Examples

Each engine has languages that it is more accurate at translating, so even when translating the same post between each engine you may see different results.

From German to English
> Das haben wir jetzt davon, daß @FrauHolle ein paar Blumen und Pralinen zum Eid al-Fitr aka #Bayram bei Nachbars vorbei gebracht hat: Ich passe bald nicht mehr durch die Türe. [https://mastodon.trueten.de/@thomas/112253624254825586](https://mastodon.trueten.de/@thomas/112253624254825586)

| | Translation |
|-|-------------|
| DeepL | This is what we get for @FrauHolle dropping off some flowers and chocolates for Eid al-Fitr aka #Bayram at neighbor's: I won't fit through the door soon. |
| LibreTranslate | We have now that @FrauHolle has a few flowers and chocolates to the Eid al-Fitr aka #Bayram brought by neighbors: I'm not gonna pass through the door soon. |
| Lingva | This is what we now have from @FrauHolle dropping off a few flowers and chocolates at a neighbor's house for Eid al-Fitr aka #Bayram: Soon I won't be able to fit through the door anymore. |

From Spanish to English
> Interesante esto, no conocía las pruebas que se están haciendo con el hormigón permeable, aunque sí vi alguno de los jardines de lluvia que está instalando la Intendencia. [https://mastodon.uy/@j3j5/112253694713024979](https://mastodon.uy/@j3j5/112253694713024979)

| | Translation |
|-|-------------|
| DeepL | Interesting this, I was not aware of the tests being done with permeable concrete, although I did see some of the rain gardens being installed by the Intendencia. |
| LibreTranslate | Interesting this, I did not know the tests being done with the permeable concrete, although I did see some of the rainy gardens that the Intendence is installing. |
| Lingva | This is interesting, I was not aware of the tests that are being done with permeable concrete, although I did see some of the rain gardens that the Municipality is installing. |

From Finnish to English
> Onko kellään kokemuksia sähköskoottereista talvikäytössä? Niistä joita alle 15 v voi ajaa Max 25 km/h. Miten akku kestää pakkaset ja onko hyviä renkaita? [https://mastodon.social/@artomelaranta/112253491123890060](https://mastodon.social/@artomelaranta/112253491123890060)

| | Translation |
|-|-------------|
| DeepL | Does anyone have any experience with electric scooters in winter use? The ones that under 15 years old can drive up to 25 km/h. How does the battery stand up to frosts and are there good tyres? |
| LibreTranslate | Does anyone have experience with electric scooters in winter? The ones below 15 can drive Max 25 km/h. How does the attery last and are there good tires? |
| Lingva | Does anyone have experience with electric scooters in winter use? Of those under 15 years of age, Max 25 km/h can be driven. How does the battery withstand frost and are there any good tires? |