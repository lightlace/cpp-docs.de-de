---
title: Benutzerdefinierte Buildschritteigenschaften (Linux C++)
ms.date: 06/07/2019
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: e09af7642171d0d73d2b06c048067bbe61290ddc
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821414"
---
# <a name="custom-build-step-properties-linux-c"></a>Benutzerdefinierte Buildschritteigenschaften (Linux C++)

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Eigenschaft | Beschreibung
--- | ---
Befehlszeile | Der vom benutzerdefinierten Buildschritt auszuführende Befehl.
Beschreibung | Eine Meldung, die anzeigt, wann der benutzerdefinierte Buildschritt läuft.
Ausgaben | Die Ausgabedatei, die der benutzerdefinierte Buildschritt generiert. Diese Einstellung ist erforderlich, damit inkrementelle Builds ordnungsgemäß funktionieren.
Zusätzliche Abhängigkeiten | Eine durch Semikolons getrennte Liste von zusätzlichen Eingabedateien, die für den benutzerdefinierten Buildschritt verwendet werden soll.
Im Anschluss ausführen und vorher ausführen | Diese Optionen definieren, wann ein benutzerdefinierter Buildschritt im Buildprozess relativ zu den aufgelisteten Zielen ausgeführt wird. Die am häufigste aufgelisteten Ziele sind BuildGenerateSources, BuildCompile und BuildLink, da sie die Hauptschritte im Buildprozess darstellen. Andere oft aufgelisteten Ziele sind Midl, CLCompile und Link.
Ausgabe als Inhalt behandeln | Diese Option ist nur bei Microsoft Store oder Windows Phone-Apps von Bedeutung, bei denen alle Inhaltsdateien im APPX-Paket enthalten sind.

::: moniker-end