# Covid Tracker
_Track the virus not the people_

## Overview
With the current worldwide pandemic, there's a drive for technical solutions to track contacts, however this is met with concerns about privacy.

This project aims to provide a solution to anonymous contact tracing. Whilst other solutions have users report identifiers for all other users that they are in contact with to a centralised server, this solution does not. Your data and your interactions are kept between yourselves, and therefore going further to protect your identity.

## How does it work?
### Contact tracking
Your phone emits a packet of data with a unique identifier, this identifier is not logged anywhere as associated with you, it is only on your phone. Any phone with this app installed that comes near your phone will record your identifier, although these phones could build a picture of all the locations your identifier has been, it is not any more of an issue than just having your bluetooth turned on.

### Reporting
If you contract coronavirus, you have the option to report the identifiers of everyone that you have been in contact with for the past 14 days, this will be entirely within your control, and would only be the important 14-day history, not your entire history.

### Contact identification 
Every day the app will get all the reported identifiers from the central service, and it will check to see if its own identifier is in this list. By collecting the full list, you maintain your anonymity.

## Additional security
The above described protocol is the minimum required to function, however a few extra steps could be taken to greatly improve the security offered.

### Rolling identifiers
Your phone can generate a new unique identifier either on request, or at an interval, whilst it isn't required except for the most privacy conscious.

### Signed reports
There is a risk of false reports causing distraction, with official buy-in the protocol can be extended to include verification by medical staff. This would affect only the reporting aspect, an authorised user will be able to generate a signing key for the report that can be used by your device to verify the report. The centralised service will then verify the signature on upload.

## Early warning extension
It would be possible to additionally match against all the recorded identifiers to provide an early warning when someone you have been in contact with has been in contact with a confirmed case. The can be used to reduce your contact for a period of time to reduce the chance of passing the virus on.

## Components

### Mobile App
The main component to this project, the mobile app will be responsible for generating the unique identifier and storing it locally. The app will set the advertising packet for Low Energy Bluetooth with the unique identifier. It will scan for other devices frequently, and record any identifier that it sees. The app will periodically check the remote server for the list of all reported identifiers, and match them against its own unique identifier. It will provide a mechanism to report a case.

#### Android App ![todo](https://img.shields.io/badge/status-TODO-lightgrey)
An Android app developed natively for this project.

#### Apple iOS App ![todo](https://img.shields.io/badge/status-TODO-lightgrey)
An IOS app developed natively for this project.

### Central at risk server ![todo](https://img.shields.io/badge/status-TODO-lightgrey)
The centralised server will accept an upload of data, and create daily rolling digest of identifiers that have been in contact with a confirmed case. The centralised server will allow these reports to be downloaded by the client. The static nature of the data distribution allows for the reports to be offloaded to a CDN service to improve performance and reduce costs.

## Contribution
Everyone is welcome to contribute to this project, please fork this repository and begin creating Pull Requests, tasks are tracked through the issues tab.

## License ![MIT](https://img.shields.io/github/license/neirfeno/covid-tracker)
This project is under the MIT license
