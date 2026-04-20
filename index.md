# Privacy Policy for Vessel

*Last updated: April 20, 2026*

Vessel is a voice journaling app built around a commitment to honesty about what happens with your words. This policy explains what data Vessel handles, where it goes, and what your rights are. It is written to be read, not to protect us from you.

## What Vessel stores on your device

Your journal entries — including transcripts, summaries, reflections, themes, and any audio files — are stored locally on your device using your operating system's secure storage. They are encrypted at rest using a hardware-backed keystore.

Your PIN, if you set one, is stored as a hash (not as readable text) and checked on each app launch. Biometric unlock, if enabled, uses your device's built-in biometric system; Vessel never sees your fingerprint or face data.

Your preferences — including your tradition choice and feature toggles — are stored locally in the same encrypted store.

## What leaves your device

When you record a voice entry and have the Transcription feature turned on, the audio file is sent over an encrypted connection to our backend server (vessel-backend.vercel.app), which forwards it to OpenAI's Whisper API for transcription. Once the transcript returns, the audio file is deleted from your device.

When you have the Reflection feature turned on, the resulting transcript is sent to Anthropic's Claude API (via our backend) along with a small amount of context from your recent entries, so Claude can generate a summary and a brief reflection. Only what is needed for that specific reflection is sent.

When you have the Companion Perspectives or Echoes features turned on, relevant entry content is sent to Claude to generate those offerings.

Our backend is a stateless proxy. It does not store your entries, transcripts, or reflections. It exists only to keep API keys secret from the app on your device.

If you turn the Transcription feature off in Settings, nothing you record leaves your phone. The audio stays on your device as a playable audio file. If you turn the Reflection feature off, transcripts are kept locally but are not sent to Claude.

## What OpenAI and Anthropic do with your data

OpenAI retains API data for up to 30 days for abuse monitoring purposes, then deletes it. They do not use API data to train their models.

Anthropic retains API data for up to 7 days in a similar way.

Both providers flag content under narrow circumstances: credible threats of harm to self or others, child sexual abuse material, requests to develop weapons, or requests to create malware. They do not flag grief, anger, emotional struggle, suicidal ideation expressed in a reflective context, or honest disclosure of difficult experiences. We tell you this because the abuse monitoring policies are a reality of using modern AI services and you deserve to know.

Their privacy practices are governed by their own policies:
- OpenAI: https://openai.com/policies/privacy-policy
- Anthropic: https://www.anthropic.com/legal/privacy

## About accounts and tracking

Vessel currently has no account system. Your entries are tied to your device, not to a user profile.

Vessel does not track your behavior in the app. There is no analytics SDK.

Vessel does not serve advertisements.

Vessel does not sell or share your data with third parties for their own purposes. The only third parties that receive any data are OpenAI and Anthropic, and only for the purpose of delivering the features you explicitly have turned on.

We do not have access to your entries. They live on your device. If you lose your phone without a backup, we cannot recover them for you.

If an account system is added in the future — for example, to enable cross-device sync or to manage distribution — this policy will be updated before that feature is made available. Your existing entries will never be tied to a new account without your explicit, informed consent.

## Your rights and controls

You can export all your entries at any time from Settings → Your data → Export. The export is a JSON file you can save, back up, and import into a fresh install.

You can delete all your data at any time from Settings → Danger zone → Delete all data.

You can turn off any feature that sends data to OpenAI or Anthropic from Settings → Features. Turning off Transcription makes Vessel an entirely on-device experience.

You can delete the app at any time. On most devices, this also deletes all local data.

## Children

Vessel is not intended for users under the age of 13. We do not knowingly collect data from children under 13. If you believe a child has used the app, please contact us and we can guide you through deleting the data from their device.

## Changes to this policy

If this policy changes in a meaningful way, we will update the "Last updated" date at the top and note the change. For early testers, you may also hear about changes directly.

## Contact

If you have questions about this policy, how your data is handled, or you want help with any of the above, reach out:

- Email: somana.dharam@gmail.com

---

*Vessel is made by one person, for now. If that changes, this policy will be updated to reflect who is responsible for your data.*
