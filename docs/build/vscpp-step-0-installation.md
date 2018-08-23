---
title: Installieren von C++-Unterstützung in Visual Studio | Microsoft-Dokumentation
description: Installieren Sie Visual Studio-Unterstützung für Visual C++
ms.custom: mvc
ms.date: 06/21/2018
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfc91d25e4c843eaa004b59eab076bcfbe188253
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42571386"
---
# <a name="install-c-support-in-visual-studio"></a>Installieren von C++-Unterstützung in Visual Studio

Wenn Sie noch nicht heruntergeladen und Visual Studio und Visual C++-Tools noch nicht installiert, sieht aus wie für den Einstieg.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Eine Breitband-Internetverbindung. Visual Studio-Installer kann mehrere Gigabyte Daten herunterladen.

- Ein Computer, der Microsoft Windows 7 oder höher ausgeführt wird. Wir empfehlen die Windows 10, für die bestmögliche entwicklungserfahrung. Stellen Sie sicher, dass die neuesten Updates für Ihr System angewendet werden, vor der Installation von Visual Studio.

- Ausreichend freier Speicherplatz auf dem Datenträger. Visual Studio erfordert mindestens 7GB Speicherplatz und dauert mindestens 50GB, wenn viele allgemeine Optionen installiert sind. Es wird empfohlen, dass Sie es auf Ihrem Laufwerk "c:" installieren.

Weitere Informationen zu den freien Speicherplatz und den Anforderungen des Betriebssystems, finden Sie unter [Visual Studio Systemanforderungen der Produktfamilie](/visualstudio/productinfo/vs2017-system-requirements-vs). Das Installationsprogramm gibt an, wie viel Speicherplatz für die Optionen erforderlich ist, die Sie auswählen.

## <a name="installation"></a>Installation

1. Laden Sie das neueste Visual Studio 2017-Installationsprogramm für Windows herunter.

   > [!div class="nextstepaction"]
   > [Installieren von Visual Studio 2017 Community](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Die Community Edition eignet sich für einzelne Entwickler, Schulungsumgebungen, akademische Forschung und Open Source-Entwicklung. Installieren Sie für andere Verwendungen [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) oder [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

1. Suchen Sie die Installer-Datei, die Sie heruntergeladen haben und ihn ausführen. Sie können in Ihrem Browser angezeigt werden, oder Umständen ist es in Ihrem Ordner "Downloads". Das Installationsprogramm benötigt Administratorrechte ausgeführt. Sie sehen möglicherweise eine **User Account Control** Dialogfeld werden Sie aufgefordert, erteilen Sie Berechtigungen zum können des Installationsprogramms, nehmen Sie Änderungen an Ihrem System aus, wählen **Ja**. Wenn Sie Probleme auftreten, suchen Sie die heruntergeladene Datei im Datei-Explorer, mit der rechten Maustaste auf das Symbol "Installer" aus, und wählen **als Administrator ausführen** aus dem Kontextmenü.

   ![Führen Sie das Visual Studio 2017-Installationsprogramm](../build/media/vscpp-concierge-run-installer.gif "führen Sie den Visual Studio-Installer")

1. Der Installer bietet Ihnen eine Liste von Workloads, bei denen es sich um Gruppen von verwandten Optionen für bestimmte Entwicklungsbereiche handelt. Unterstützung für C++ ist jetzt Teil der optionalen Workloads, die standardmäßig installiert sind.

   ![Desktopentwicklung mit C++](../build/media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

    Wählen Sie für C++, die **Desktopentwicklung mit C++** Workload und wählen Sie dann **installieren**.

   ![Installieren Sie die Desktopentwicklung mit C++-Arbeitslast](../build/media/vscpp-concierge-choose-workload.gif "installieren Sie die Desktopentwicklung mit C++-Arbeitslast")

1. Wählen Sie nach Abschluss der Installation der **starten** Schaltfläche zum Starten von Visual Studio.

   Beim ersten Ausführen von Visual Studio werden Sie aufgefordert, sich mit einem Microsoft Account anmelden. Wenn Sie über keins verfügen, können Sie es kostenloses erstellen. Sie müssen auch ein Design auswählen. Keine Sorge, Sie können ihn später ändern, wenn Sie möchten. 

   Es dauert Visual Studio mehrere Minuten auf vorzubereiten verwenden den ersten, die sie ausführen. So sieht es wie in der eine schnelle, die mit:

   ![Melden Sie sich bei Visual Studio 2017](../build/media/vscpp-quickstart-first-run.gif "melden Sie sich bei Visual Studio 2017")

   Visual Studio startet viel schneller, wenn Sie es erneut ausführen.

1. Wenn Visual Studio geöffnet wird, überprüfen Sie, wenn markiert ist, dass Sie das Symbol in der Titelleiste an:

   ![Visual Studio 2017-Benachrichtigungskennzeichen](../build/media/vscpp-first-start-page-flag.png "Benachrichtigungshinweis für Visual Studio 2017")

   Wenn er hervorgehoben wird, wählen Sie diese zum Öffnen der **Benachrichtigungen** Fenster. Wenn keine Updates für Visual Studio verfügbar sind, empfehlen wir, dass Sie dies jetzt tun. Sobald die Installation abgeschlossen ist, starten Sie Visual Studio neu.

Wenn Visual Studio ausgeführt wird, können Sie mit dem nächsten Schritt fortfahren.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erstellen Sie ein C++-Projekt](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
