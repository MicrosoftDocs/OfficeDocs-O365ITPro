---
title: URLs and address ranges for Kaizala
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
audience: Admin
ms.date: 3/11/2020
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.reviewer: nitinjms2
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to configure URLs and IP address ranges for connectivity in Kaizala.
---

# URLs and address ranges for Kaizala

Microsoft Kaizala requires connectivity to the internet. Organizations, if required by firewall protections, must allow certain IP addresses and URLs to enable their users to access the Kaizala app and its services.

> [!NOTE]
> Endpoint data might also be updated if needed to address support escalations, security incidents, or other immediate operational requirements.

The following table shows endpoint URLs and IP address ranges required for connectivity from a user’s device to Kaizala and related services. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.

| No. | Endpoint URLs | IP addresses | Port | Notes|
|--------|-----|-----------|----|------------|
| 1 | Kms*.kaiza.la |52.172.209.57, 52.172.24.172, 23.100.79.167, 40.74.230.57, 213.199.139.160, 52.138.202.218, 13.67.68.49, 207.46.148.171   |443 | These are static IP addresses for Kaizala Service |
| 2 | Api*.kaiza.la |13.71.17.159, 104.44.133.47, 40.85.82.252, 13.67.68.244   |443 | These are static IP addresses for accessing Kaizala through API |
| 3 | manage*.kaiza.la, join.kaiza.la, j.kaiza.la, webapp.kaiza.la |  |443 | These are static IP addresses for Kaizala management portal, Kaizala web app, and joining URLs |
| 4 | cdn.inc-000.kms.osi.office.net, cdn.ins-000.kms.osi.office.net, cdn.scus-000.kms.osi.office.net, cdn.ncus-000.kms.osi.office.net, cdn.kascore-neu.osi.office.net, cdn.kascore-weu.osi.office.net, cdn.kascore-sea.osi.office.net, cdn.kascore-ea.osi.office.net, osiziinclysithea001.blob.core.windows.net | |443 | Used for mostly storing documents and images generated within Kaizala |
| 5 | webshell.suite.office.com, portal.office.com, dc.services.visualstudio.com, browser.pipe.aria.microsoft.com, embedded.powerbi.com, *.analysis.windows.net, r1.res.office365.com, d3js.org | |443 | Needed for enabling Office 365 services (including PowerBI reports) and other features on Kaizala management portal |
| 6 | api.cc.skype.com, app.adjust.com, c-broker-asse-01.broker.skype.com, fef.bmsua01.manage-beta.microsoft.com, gate.hockeyapp.net, go.microsoft.com, graph.microsoft.com, gsp64-ssl.ls.apple.com, gspe19-ssl.ls.apple.com, gspe35-ssl.ls.apple.com, gsp-ssl.ls.apple.com, login.microsoftonline.com, login.windows.net, mobile.pipe.aria.microsoft.com, mobileonlyapps.blob.core.windows.net, osizpinccolumba003.blob.core.windows.net, osizpinckallichore008.blob.core.windows.net, osizpinclysithea001.blob.core.windows.net, privacy.microsoft.com, prod.registrar.skype.com, trap.skype.com, vortex.data.microsoft.com | |443 | Other URLs needed to allow Kaizala app to operate normally |
