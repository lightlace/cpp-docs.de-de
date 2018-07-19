---
title: Benutzerdefinierte Buildschritteigenschaften (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/17/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 0ec787826a09379732ac00fa858d32f05cf8025b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326071"
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