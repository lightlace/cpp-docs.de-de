---
title: Benutzerdefinierte Buildschritteigenschaften (Linux C++) | Microsoft Docs
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: b46ee18fce79c0e1954d37a87f6380c73870fa12
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="custom-build-step-properties-linux-c"></a>Benutzerdefinierte Buildschritteigenschaften (Linux C++)

Eigenschaft | description
--- | ---
Befehlszeile | Der vom benutzerdefinierten Buildschritt auszuführende Befehl.
description | Eine Meldung, die anzeigt, wann der benutzerdefinierte Buildschritt läuft.
Ausgaben | Die Ausgabedatei, die der benutzerdefinierte Buildschritt generiert. Diese Einstellung ist erforderlich, damit inkrementelle Builds ordnungsgemäß funktionieren.
Zusätzliche Abhängigkeiten | Eine durch Semikolons getrennte Liste von zusätzlichen Eingabedateien, die für den benutzerdefinierten Buildschritt verwendet werden soll.
Im Anschluss ausführen und vorher ausführen | Diese Optionen definieren, wann ein benutzerdefinierter Buildschritt im Buildprozess relativ zu den aufgelisteten Zielen ausgeführt wird. Die am häufigste aufgelisteten Ziele sind BuildGenerateSources, BuildCompile und BuildLink, da sie die Hauptschritte im Buildprozess darstellen. Andere oft aufgelisteten Ziele sind Midl, CLCompile und Link.
Ausgabe als Inhalt behandeln | Diese Option ist nur bei Microsoft Store oder Windows Phone-Apps von Bedeutung, bei denen alle Inhaltsdateien im APPX-Paket enthalten sind.