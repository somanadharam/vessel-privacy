# Privacy Policy for Vessel

*Last updated: May 12, 2026*

Vessel is a voice journaling app built around a commitment to honesty about what happens with your words. This policy explains what data Vessel handles, where it goes, and what your rights are. It is written to be read, not to protect us from you.

## What Vessel stores on your device

Your journal entries — including transcripts, summaries, reflections, themes, and any audio files in flight — are stored locally on your device in your operating system's encrypted application storage. The entries themselves are encrypted with AES-GCM using a 256-bit key. That key is held in your phone's secure keystore (Keychain on iOS, Keystore on Android), which is hardware-backed on modern devices. The encrypted entries are stored separately from the key.

Your PIN, if you set one, is stored as a hash (not as readable text) and checked on each app launch. Biometric unlock, if enabled, uses your device's built-in biometric system; Vessel never sees your fingerprint or face data.

Your preferences — including your tradition choice and feature toggles — are stored locally in the same encrypted store.

## What leaves your device

Vessel uses two stateless backend services that exist only to talk to AI providers on your behalf. They do not store your entries, transcripts, audio, or reflections.

When you record a voice entry and have the Transcription feature turned on, the audio file is sent over an encrypted connection to a Cloudflare Worker (vessel-transcribe.somanadharam.workers.dev), which forwards it to OpenAI's Whisper API for transcription. The audio is held in worker memory only for the duration of that request. Once the transcript returns, the audio file is also deleted from your device.

When you have the Reflection feature turned on, the resulting transcript is sent to Anthropic's Claude API (via a separate Vercel function at vessel-backend.vercel.app) along with a small amount of context from your recent entries, so Claude can generate a summary and a brief reflection. Only what is needed for that specific reflection is sent.

When you have the Echoes feature turned on, relevant entry content is sent to Claude to surface past entries that may resonate with what you just recorded.

If you turn the Transcription feature off in Settings, nothing you record leaves your phone. The audio stays on your device as a playable audio file. If you turn the Reflection feature off, transcripts are kept locally but are not sent to Claude.

## What OpenAI and Anthropic do with your data

OpenAI retains API data for up to 30 days for abuse monitoring purposes, then deletes it. They do not use API data to train their models.

Anthropic retains API data for up to 7 days in a similar way.

Both providers flag content under narrow circumstances: credible threats of harm to self or others, child sexual abuse material, requests to develop weapons, or requests to create malware. They do not flag grief, anger, emotional struggle, suicidal ideation expressed in a reflective context, or honest disclosure of difficult experiences. We tell you this because the abuse monitoring policies are a reality of using modern AI services and you deserve to know.

Their privacy practices are governed by their own policies:
- OpenAI: https://openai.com/policies/privacy-policy
- Anthropic: https://www.anthropic.com/legal/privacy

## About accounts and authentication

Vessel does not have a traditional account system. There is no email, no password, no profile.

When you first open the app, it generates an anonymous random credential and stores it in your phone's secure keystore. A copy is also kept in our backend's lookup table so we can recognize valid credentials when they call. The credential is sent with API requests so that our backends know "this is a Vessel device" rather than an arbitrary caller. It does not identify you. We do not know your name, your email, your location, or anything else about you. If your credential is compromised, we can revoke it individually without affecting other users.

The credential is per-device. If you install Vessel on a second device, that device generates its own credential. There is no cross-device sync of entries — each device's journal lives only on that device. This is intentional.

Vessel does not track your behavior in the app. There is no analytics SDK.

Vessel does not serve advertisements.

Vessel does not sell or share your data with third parties for their own purposes. The only third parties that receive any data are OpenAI and Anthropic, and only for the purpose of delivering the features you explicitly have turned on.

We do not have access to your entries. They live on your device. If you lose your phone without a backup, we cannot recover them for you. This is the deliberate cost of an architecture where your entries never sit on our servers.

If a richer account system is added in the future — for example, to enable cross-device sync — this policy will be updated before that feature is made available. Your existing entries will never be moved off-device without your explicit, informed consent.

## A note on what authentication does and doesn't protect

The anonymous credential lets us rate-limit and revoke per device. It does not turn Vessel into an authenticated user system in the conventional sense. Specifically:

The credential does not protect your entries from someone with physical access to your unlocked phone — that is what the PIN and biometric unlock are for.

The credential does not encrypt your data — that is what the AES-GCM encryption does locally.

The credential does not protect against the realities of the AI providers we use — that is governed by their policies, disclosed above.

We mention this so that "anonymous device credential" doesn't sound like more than it is. It is a small, useful operational primitive, not a magic shield.

## Your rights and controls

You can export all your entries at any time from Settings → Your data → Export. The export is a JSON file you can save, back up, and import into a fresh install. We recommend exporting periodically.

You can delete all your data at any time from Settings → Danger zone → Delete all data.

You can turn off any feature that sends data to OpenAI or Anthropic from Settings → Features. Turning off Transcription makes Vessel an entirely on-device experience.

You can delete the app at any time. On most devices, this also deletes all local data.

## Payment

*Placeholder — payment is not yet implemented. This section will be filled in before any paid tier ships. When it does, this policy will be updated to disclose Apple's or Google's role as payment processor, what information is exchanged with them, and what refund and cancellation policies apply.*

## Children

Vessel is not intended for users under the age of 13. We do not knowingly collect data from children under 13. If you believe a child has used the app, please contact us and we can guide you through deleting the data from their device.

## Changes to this policy

If this policy changes in a meaningful way, we will update the "Last updated" date at the top and note the change. For early testers, you may also hear about changes directly.

## Contact

If you have questions about this policy, how your data is handled, or you want help with any of the above, reach out:

- Email: somana.dharam@gmail.com

---

*Vessel is made by one person, for now. If that changes, this policy will be updated to reflect who is responsible for your data.*