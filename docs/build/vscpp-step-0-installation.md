---
title: "C++-Unterstützung in Visual Studio zu installieren | Microsoft Docs"
description: "Installieren Sie Visual Studio-Unterstützung für Visual C++"
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b895569e5535fb05c1e2383df224f149815dd47f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="install-c-support-in-visual-studio"></a>C++-Unterstützung in Visual Studio installieren

Wenn Sie noch nicht heruntergeladen und installiert noch Visual Studio und Visual C++-Tools, sieht die erste Schritte.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Einer breitbandinternetverbindung. Visual Studio-Installer kann mehrere Gigabyte an Daten herunterladen.

- Ein Computer, der Microsoft Windows 7 oder höher ausgeführt wird. Wir empfehlen Windows 10 Entwicklung optimale Ergebnisse zu erzielen. Stellen Sie sicher, dass die neuesten Updates vor der Installation von Visual Studio auf das System angewendet werden.

- Ausreichend freier Speicherplatz vorhanden. Visual Studio erfordert mindestens 7GB Speicherplatz und dauert mindestens 50GB, wenn viele allgemeine Optionen installiert werden. Es wird empfohlen, dass die Installation auf dem Laufwerk "c:".

Ausführliche Informationen zu den freien Speicherplatz und die Anforderungen an das Betriebssystem, finden Sie unter [Systemanforderungen für Visual Studio 2017](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs). Das Installationsprogramm gibt an, wie viel Speicherplatz für die Optionen erforderlich ist, die Sie auswählen.

## <a name="installation"></a>Installation

1. Laden Sie das neueste Visual Studio 2017-Installationsprogramm für Windows herunter.

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Installieren von Visual Studio 2017 Community</a>

   >[!Tip]
   > Die Community Edition eignet sich für einzelne Entwickler, Schulungsumgebungen, akademische Forschung und Open Source-Entwicklung. Installieren Sie für andere Verwendungen <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Professional</a> oder <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Enterprise</a>.

1. Suchen Sie die Installationsdatei heruntergeladen und führen Sie es. Kann in Ihrem Browser angezeigt werden, oder Sie finden es vielleicht in Ihrem Ordner "Downloads". Das Installationsprogramm benötigt Administratorrechte zum Ausführen. Sie wird möglicherweise eine **User Account Control** Dialogfeld bestätigen Sie gewähren der Berechtigung, lassen das Installationsprogramm, nehmen Sie Änderungen an Ihrem System aus, wählen Sie **Ja**. Wenn Sie Probleme haben, suchen Sie die heruntergeladene Datei im Datei-Explorer mit der rechten Maustaste auf das Symbol "Installationsprogramm", und wählen **als Administrator ausführen** aus dem Kontextmenü.

   ![Führen Sie das Installationsprogramm von Visual Studio 2017](../build/media/vscpp-concierge-run-installer.gif "führen Sie das Installationsprogramm von Visual Studio")

1. Der Installer bietet Ihnen eine Liste von Workloads, bei denen es sich um Gruppen von verwandten Optionen für bestimmte Entwicklungsbereiche handelt. Unterstützung für C++ ist jetzt Teil des optionalen Arbeitslasten, die standardmäßig installiert sind.

   ![Desktop-Entwicklung mit C++](../build/media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

    Wählen Sie für C++, die **Desktopentwicklung mit C++** Arbeitslast und wählen Sie dann **installieren**.

   ![Installieren Sie die Desktopentwicklung C++ Arbeitslast](../build/media/vscpp-concierge-choose-workload.gif "installieren Sie die Desktop-Entwicklung mit C++-Arbeitslast")

1. Wählen Sie nach Abschluss der Installation der **starten** Schaltfläche, um Visual Studio starten.

   Beim erstmaligen Ausführen von Visual Studio werden Sie aufgefordert, zur Anmeldung mit einem Microsoft-Account. Wenn Sie über keins verfügen, können Sie es kostenloses erstellen. Sie müssen zudem ein Design auswählen. Keine Sorge, Sie können ihn später ändern Sie nach Bedarf. 

   Dauert möglicherweise Visual Studio einige Minuten, um für die Verwendung der ersten Ausführung vorzubereiten. Hier ist, wie es in einer kurzen Zeitraffervideos aussieht:

   ![Melden Sie sich bei Visual Studio 2017](../build/media/vscpp-quickstart-first-run.gif "2017 von Visual Studio anmelden")

   Visual Studio startet viel schneller, wenn Sie es erneut ausführen.

1. Überprüfen Sie beim Öffnen von Visual Studio, um festzustellen, ob das Flagsymbol in der Titelleiste hervorgehoben ist:

   ![Visual Studio 2017 Benachrichtigungskennzeichen](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 Benachrichtigungskennzeichen")

   Wenn er hervorgehoben wird, wählen Sie diese so öffnen die **Benachrichtigungen** Fenster. Wenn alle Updates für Visual Studio verfügbar sind, wird empfohlen, dass Sie diese jetzt installieren. Sobald die Installation abgeschlossen ist, starten Sie Visual Studio neu.

Wenn Visual Studio ausgeführt wird, werden Sie mit dem nächsten Schritt fortfahren.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erstellen Sie ein C++-Projekt](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
