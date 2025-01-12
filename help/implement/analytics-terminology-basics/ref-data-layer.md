---
description: A "data layer" is a framework of JavaScript objects that developers insert into pages.
keywords: Analytics Implementation;data layer;digitalData
solution: Analytics
title: Data Layer
topic: Developer and implementation
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
---

# Data Layer

A _data layer_ is a framework of JavaScript objects that developers insert into pages. The data layers can be used by tracking tools (including tag management systems like Adobe Experience Platform Launch and Dynamic Tag Management) to populate reports.

Implementing a data layer on your site provides ultimate control and flexibility over your implementation and allows easiest maintenance in future phases​. The names of these JavaScript objects are theoretically arbitrary, but the best practice is to use something consistent and predictable. The developers might already have a data layer, or a preference for the format. There are few different standards the tracking community has created as a starting point. The [Data Layer for Analytics Implementation](assets/datalayer-documentation.pdf) specification document uses the W3C standard "digitalData" object that is accepted by the widest variety of tracking technology, in case there is a need to use the data layer for more than this DTM implementation.
