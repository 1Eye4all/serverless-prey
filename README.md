# Puma Scan Serverless Prey

Serverless Prey is a collection of serverless functions (FaaS), that, once launched to a cloud environment and invoked, establish a TCP reverse shell, enabling the user to introspect the underlying container:

* [Panther](panther): AWS Lambda written in Node.js
* [Cougar](cougar): Azure Function written in C#
* [Cheetah](cheetah): Google Cloud Function written in Go

This repository also contains research performed using these functions, including documentation on where secrets are stored, how to extract sensitive data, and identify monitoring / incident response data points.

![Diagram](diagram.png "Diagram")

## Disclaimer

**Serverless Prey functions are intended for research purposes only and should not be deployed to production accounts.** By their nature, they provide shell access to your runtime environment, which can be abused by a malicious actor to exfiltrate sensitive data or gain unauthorized access to related cloud services.

## Contributors

[Eric Johnson](https://github.com/ejohn20) - Principal Security Engineer, Puma Security

[Brandon Evans](https://github.com/BrandonE) - Senior Application Security Engineer, Asurion

## Learning More

* Watch Eric Johnson discuss the motivation and results of this research at RSAConference2020 in ["Defending Serverless Infrastructure in the Cloud"](https://www.youtube.com/watch?v=tlZ2PIXTHxc).

* Download the RSAConference2020 [Defending Serverless Infrastructure in the Cloud](https://published-prd.lanyonevents.com/published/rsaus20/sessionsFiles/17433/2020_USA20_CSV-T12_01_Defending%20Serverless%20Infrastructure%20in%20the%20Cloud.pdf) slides.
