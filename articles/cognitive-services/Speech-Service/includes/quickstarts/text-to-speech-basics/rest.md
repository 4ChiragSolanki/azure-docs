---
author: eric-urban
ms.service: cognitive-services
ms.topic: include
ms.date: 03/15/2022
ms.author: eur
---

[!INCLUDE [Header](../../common/rest.md)]

[!INCLUDE [Introduction](intro.md)]

## Prerequisites

[!INCLUDE [Prerequisites](../../common/azure-prerequisites.md)]

> [!div class="nextstepaction"]
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0Cl5zkG3CnDjq6O?PLanguage=REST&Pillar=Speech&Product=text-to-speech&Page=quickstart&Section=Prerequisites" target="_target">I ran into an issue</a>

## Synthesize to a file

At a command prompt, run the following cURL command. Insert the following values into the command. Replace `YourSubscriptionKey` with your Speech resource key, and replace `YourServiceRegion` with your Speech resource region. Optionally you can rename `output.mp3` to another output filename.

```console
key="YourSubscriptionKey"
region="YourServiceRegion"

curl --location --request POST 'https://$region.tts.speech.microsoft.com/cognitiveservices/v1' \
--header 'Ocp-Apim-Subscription-Key: $key' \
--header 'Content-Type: application/ssml+xml' \
--header 'X-Microsoft-OutputFormat: audio-16khz-128kbitrate-mono-mp3' \
--header 'User-Agent: curl' \
--data-raw '<speak version='\''1.0'\'' xml:lang='\''en-US'\''>
    <voice xml:lang='\''en-US'\'' xml:gender='\''Female'\'' name='\''en-US-JennyNeural'\''>
        my voice is my passport verify me
    </voice>
</speak>' > output.mp3
```

The provided text should be output to an audio file named output.mp3.

To change the speech synthesis language, replace `en-US-JennyNeural` with another [supported voice](~/articles/cognitive-services/speech-service/supported-languages.md#prebuilt-neural-voices). All neural voices are multilingual and fluent in their own language and English. For example, if the input text in English is "I'm excited to try text to speech" and you set `es-ES-ElviraNeural`, the text is spoken in English with a Spanish accent. If the voice does not speak the language of the input text, the Speech service won't output synthesized audio.

For more information, see [speech-to-text REST API for short audio](../../../rest-speech-to-text.md).

> [!div class="nextstepaction"]
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0Cl5zkG3CnDjq6O?PLanguage=REST&Pillar=Speech&Product=text-to-speech&Page=quickstart&Section=Synthesize-to-file-output" target="_target">I ran into an issue</a>


## Clean up resources

[!INCLUDE [Delete resource](../../common/delete-resource.md)]
