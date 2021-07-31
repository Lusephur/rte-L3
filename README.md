# rte-L3
This is based fully on the work of fullonranger and a concept for testing security of Widevine-L3 encryption.   
It is meant to be used with Widevine-L3-Guesser which was compiled recently late July 2021 by https://github.com/Satsuoni.

Currently not working with Virgin Media Player or TG4.

# Prerequisites
1. `pip install -r requirements.txt`

2. Download the Selenium Chrome WebDriver [here](https://chromedriver.chromium.org/downloads) and paste it in the rte-L3 folder. You must have Google Chrome installed. **Note this only works with Versions of Chrome from 89 or 90 upward**.  Also ensure that the version of the webdriver matches that of the Chrome version you have installed. 

3. Download Widevine-L3 guesser here https://github.com/Satsuoni/widevine-l3-guesser
In the decryptor's "content_key_decryption.js" on line 251 - **console.log**("WidevineDecryptor: Found key:....... " replace it with **document.write**("WidevineDecryptor: Found key: " + toHexString(decryptedKey) + " (KID=" + toHexString(keyId) + ")");`.

4. Remove the log parsing and memory dump folders from the downloaded git folder. Not sure if this is necessary but they caused me issues with loading the decryptor.

5. In Chrome, go to the Extensions page and click "Pack extension". Enter the location of the widevine decryptor folder with the modified content_key_decryption.js.

6. Save the output file as "decryptor**1**.crx" Paste the outputted .crx file in the rte-L3 folder and rename it to "decryptor**1**.crx".

# How to use
`rtel3.py "URL"`

# Disclaimer
This is for educational and security testing purposes only. According to RTÉ's terms of service, "You may not broadcast, copy, download, frame, reproduce, republish, post, transmit, merge, edit, adapt, resell, re-use, produce summaries or otherwise use RTÉ.ie and/or its content in any way **except for your own personal, non-commercial, non- business use**." Use at your own risk.
