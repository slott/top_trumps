# Privacy Policy for Top Trumps

**Last Updated:** April 10, 2026

This Privacy Policy describes how Top Trumps (the "App") collects, uses, and protects your information. The App is developed and published by dk.slott_hansen ("we", "us", or "our").

By downloading, installing, or using the App, you agree to the terms of this Privacy Policy.

## 1. Information We Collect

Top Trumps is designed with privacy in mind. We minimize the data we collect:

### a) No Personal Data Collected by Us
We do not require you to create an account, nor do we ask for, collect, or store personal information such as your name, email address, phone number, or physical address on our servers. 

The "Player Name" you enter in the App is stored **locally on your device** using Android SharedPreferences and is only shared temporarily with other players during an active multiplayer session.

### b) Permissions Required for Gameplay
To enable the "Invisible Pairing" local multiplayer feature (which allows you to play with friends without an internet connection or shared router), the App utilizes the **Google Nearby Connections API**. This API requires the following device permissions:

*   **Location Permissions (ACCESS_COARSE_LOCATION / ACCESS_FINE_LOCATION):** Required by Android to discover nearby devices via Bluetooth and Wi-Fi Direct. **We do not track, record, or store your physical location.**
*   **Bluetooth Permissions (BLUETOOTH_SCAN, BLUETOOTH_ADVERTISE, BLUETOOTH_CONNECT):** Required to broadcast your game lobby and discover other players nearby.
*   **Wi-Fi Permissions (NEARBY_WIFI_DEVICES, ACCESS_WIFI_STATE, CHANGE_WIFI_STATE):** Required to establish high-speed, secure local connections between devices to synchronize game state and card decks.

## 2. How We Use the Information

Any data accessed via the permissions listed above is used **strictly for local gameplay functionality**:
*   To discover nearby devices running the App.
*   To establish a direct, peer-to-peer (P2P) connection between the Host and joining players.
*   To transmit temporary game state (e.g., your display name, selected stats, and card data) between connected devices during an active match.

## 3. Data Sharing and Third Parties

We **do not** sell, trade, or otherwise transfer any of your information to outside parties. 
Because the multiplayer functionality relies on Google's Nearby Connections API, some non-identifiable technical data may be processed by Google Play Services on your device to facilitate the connection. You can review Google's privacy policy at: https://policies.google.com/privacy

## 4. Security

We take reasonable measures to protect your information. The App communicates directly between devices using peer-to-peer protocols facilitated by the Google Nearby Connections API, which encrypts the data in transit between connected players.

## 5. Children's Privacy

This App does not knowingly collect or solicit personal information from anyone under the age of 13. Because we do not collect personal data on our servers, no such information is stored by us. If you are a parent or guardian and you believe that your child has provided us with personal information, please contact us.

## 6. Content Disclaimer and Copyright

The App functions as a dynamic platform that retrieves and displays content (including card data and images) from external, third-party URLs and repositories. We do not host, own, or control this external content. Consequently, the App and its developers are not responsible for the copyright status, legality, or accuracy of any content loaded from these third-party sources. Users are solely responsible for any content they choose to access, link to, or distribute through the App.

## 7. Changes to This Privacy Policy

We may update our Privacy Policy from time to time. We will notify you of any changes by updating the "Last Updated" date at the top of this policy and publishing the new policy on this page.

## 8. Contact Us

If you have any questions or suggestions about our Privacy Policy, do not hesitate to contact us at:

**Developer:** Morten Slott Hansen
**Contact Email:** slott.hansen@gmail.com
