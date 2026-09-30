# Speech in Spiral

Install the [Mac app](https://github.com/edtireli/spiralChat/releases/latest) and
get ordinary chat working first. Your Mac runs the speech models; Android uses
the same paired connection.

## Install transcription and translation

1. Open **plugins** on Mac, or **settings → Plugins** on Android.
2. Choose **Transcription**. Search for an MLX Whisper model or select **My model folder**.
3. Choose where to store it, review the size and licence, then **Install model & runtime**.
4. When ready, choose **Enable plugin**.
5. Open **Live transcription → Original only → Start listening** and allow microphone access.
6. For translation, install and enable a compatible MLX TranslateGemma model under
   **plugins → Translation**, then select a language in **Translate to**.

You choose the models and folders. See [supported formats](../README.md#plugin-models).
A GGUF chat model cannot substitute for a speech model. Keep external drives mounted.

## Spoken translation

Turn on **Read aloud** to hear finished translated phrases. It uses an offline
system voice installed on your phone or Mac. Install the relevant language's voice
pack in your device settings if prompted. Chat reply voices are configured separately.

Words appear provisionally while you speak and may be corrected as more audio arrives.
Spoken output waits for a finished phrase. Use headphones to avoid transcribing the
speaker's output. Copy text you want to keep; the live transcript is held in screen memory.

## Your own models and voices

Choose **My model folder** inside the relevant plugin and select a compatible model
directory on your Mac. The picker checks its format before installation. For chat
read-aloud voices, **plugins → Text to speech** supports MLX Qwen3-TTS CustomVoice
conversions; available speakers come from the selected model.

Existing custom voice services can still be selected through voice settings. They
must support Spiral's speech protocol; a generic TTS endpoint or an arbitrary voice
adapter is not automatically compatible. Live translation's **Read aloud** uses
system voices, not those custom chat voices.

Plugin selections live at `~/.spiralchat/plugins/plugins.json`; models and runtimes
stay in the folder you chose. Older manually configured speech services may use
`~/.spiralchat/translation/`. You do not need to reinstall a working service.

## If nothing appears

Check the model is enabled, microphone access is allowed, the Mac is awake, and any
external model drive is mounted. Fix ordinary chat connectivity first if the phone
cannot reach the Mac. No additional public port is needed for speech. See the
[connection walkthrough](../README.md#connect-your-phone).

Speech shares the Mac's inference lane with chat. Other local work may wait while
transcription is active. Stop listening before starting another model task. Available
languages depend on the chosen models and installed device voices.
