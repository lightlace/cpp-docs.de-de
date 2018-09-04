---
title: Profilgesteuerte Optimierung im Leistungs- und Diagnosehub | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: dc3a1914-dbb6-4401-bc63-10665a8c8943
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 275d65cdf4f0f5986ff80e65898732dadbd5f61f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691094"
---
# <a name="profile-guided-optimization-in-the-visual-studio-2013-performance-and-diagnostics-hub"></a>Profilgesteuerte Optimierung im Visual Studio 2013-Leistung und Diagnose-Hub

Wenn Sie Visual Studio 2013 verwenden, vereinfacht die profilgesteuerte Optimierung für Visual C++-Plug-in im Leistungs- und Diagnosehubs die profilgesteuerte Optimierung für Entwickler. Sie können [downloaden Sie das plug-in](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) aus Visual Studio-Website. Das plug-in wird in späteren Versionen von Visual Studio nicht unterstützt.

Mit der profilgesteuerten Optimierung (PGO) können Sie Builds systemeigener x86- und x64-Apps erstellen, die für die Interaktion mit den Benutzern optimiert sind. Profilgesteuerte Optimierung ist ein mehrstufiger Prozess: Sie erstellen eine app-Builds, die für die profilerstellung instrumentiert ist, und führen Sie "Training". Das heißt, führen Sie die instrumentierte app mit gängigen benutzerinteraktionsszenarien. Sie speichern die aufgezeichneten Profilerstellungsdaten und erstellen dann die App erneut unter Verwendung der Ergebnisse, um die Optimierung des gesamten Programms zu steuern. Sie können diese Schritte zwar auch einzeln in Visual Studio oder in der Befehlszeile ausführen, das Plug-In für die profilgesteuerte Optimierung zentralisiert und vereinfacht jedoch den Prozess. Das Plug-In für die profilgesteuerte Optimierung legt alle erforderlichen Optionen fest und führt Sie durch jeden Schritt. Es zeigt Ihnen die Analyse und verwendet anschließend die Ergebnisse, um den Build zu konfigurieren und so jede Funktion im Hinblick auf Größe oder Geschwindigkeit zu optimieren. Das Plug-In für die profilgesteuerte Optimierung macht es auch einfacher, Ihre App-Aus- und Weiterbildung erneut auszuführen und die Build-Optimierungsdaten bei Änderung des Code zu aktualisieren.

## <a name="prerequisites"></a>Erforderliche Komponenten

Sie müssen [-Plug-In für die profilgesteuerte Optimierung herunterladen](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) und in Visual Studio installieren, bevor Sie es im Leistungs- und Diagnosehub verwenden können.

## <a name="walkthrough-using-the-pgo-plug-in-to-optimize-an-app"></a>Exemplarische Vorgehensweise: Verwenden des Plug-In für die profilgesteuerte Optimierung, um eine Anwendung zu optimieren

Zuerst erstellen Sie eine einfache Win32-Desktop-App in Visual Studio. Wenn Sie bereits über eine systemeigene App verfügen, die Sie optimieren möchten, können Sie diese verwenden und diesen Schritt überspringen.

### <a name="to-create-an-app"></a>So erstellen Sie eine App

1. Wählen Sie in der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Klicken Sie im linken Bereich die **neues Projekt** Dialogfeld erweitern Sie **installiert**, **Vorlagen**, **Visual C++**, und wählen Sie dann  **MFC**.

1. Wählen Sie im mittleren Bereich **MFC-Anwendung**.

1. Geben Sie einen Namen für das Projekt, z. B. **SamplePGOProject**– in der **Namen** Feld. Klicken Sie auf die Schaltfläche **OK** .

1. Auf der **Übersicht über die** auf der Seite die **MFS-Anwendungsassistenten** Dialogfeld auf die **Fertig stellen** Schaltfläche.

Legen Sie anschließend die Buildkonfiguration der App auf „Freigabe“ fest, um sie für die PGO-Build- und -Trainingsschritte vorzubereiten.

### <a name="to-set-the-build-configuration"></a>So legen Sie die Buildkonfiguration fest

1. Wählen Sie auf der Menüleiste die Option **Erstellen**und dann **Konfigurations-Manager**aus.

1. In der **Configuration Manager** Dialogfeld auf die **aktive Projektmappenkonfiguration** Dropdown-Schaltfläche, und wählen **Version**. Wählen Sie die **schließen** Schaltfläche.

Öffnen Sie die Leistung und Diagnose-Hub, wählen Sie auf der Menüleiste **analysieren**, **Leistungs- und Diagnosehub**. Dadurch wird eine Diagnosesitzungsseite geöffnet. Diese enthält die Analysetools, die für den Projekttyp verfügbar sind.

![Profilgesteuerte Optimierung im Leistungs- und Diagnosehub](../../build/reference/media/pgofig0hub.png "PGOFig0Hub")

In **verfügbaren Tools**, wählen die **Profilgesteuerte Optimierung** Kontrollkästchen. Wählen Sie die **starten** Schaltfläche, um die profilgesteuerte Optimierung-Plug-in starten.

![PGO-Einführungsseite](../../build/reference/media/pgofig1start.png "PGOFig1Start")

Die **Profilgesteuerte Optimierung** Seite beschreibt die Schritte zur Verbesserung der Leistung Ihrer App das plug-in verwendet. Wählen Sie die **starten** Schaltfläche.

![PGO-instrumentierungsseite](../../build/reference/media/pgofig2instrument.png "PGOFig2Instrument")

In der **Instrumentation** Abschnitt, die Sie verwenden die **Training wird anfänglich aktiviert** Option zu entscheiden, ob die Anlaufphase der app als Teil des Trainings enthalten. Wenn diese Option nicht ausgewählt ist, werden die Aus- und Weiterbildungsdaten nicht in einer ausgeführten instrumentierten App aufgezeichnet, bis Sie die Aus- und Weiterbildung explizit aktivieren.

Wählen Sie die **Instrumentieren** Schaltfläche, um Ihre app mit einem bestimmten Satz von Compileroptionen zu erstellen. Der Compiler fügt Testanweisungen im generierten Code ein. Durch diese Anweisungen werden Profilerstellungsdaten während der Aus- und Weiterbildungsphase aufgezeichnet.

![PGO-Seite über instrumentierte Builds](../../build/reference/media/pgofig3build.PNG "PGOFig3Build")

Wenn das instrumentierte Build der App abgeschlossen ist, wird die App automatisch gestartet.

Wenn Fehler oder Warnungen während des Builds auftreten, korrigieren Sie diese, und wählen Sie dann **Build neu** den instrumentierten Build neu starten.

Wenn Ihre app gestartet wird, können Sie die **Schulung starten** und **Pause Training** verknüpft die **Training** Abschnitt aus, um zu steuern, wann Profilerstellungsinformationen aufgezeichnet wird. Sie können die **Anwendung beenden** und **Anwendung starten** Links zu beenden und Neustarten die app.

![PGO-Trainingsseite](../../build/reference/media/pgofig4training.PNG "PGOFig4Training")

Gehen Sie während der Aus- und Weiterbildung die Benutzerszenarios durch, um die Profilerstellungsinformationen zu erfassen, die das Plug-In für die profilgesteuerte Optimierung benötigt, um den Code zu optimieren. Wenn Sie die Schulung abgeschlossen haben, schließen Sie Ihre app, oder wählen Sie die **Anwendung beenden** Link. Wählen Sie die **analysieren** Schaltfläche, um den Analyseschritt zu starten.

Wenn die Analyse abgeschlossen ist, ist die **Analysis** Abschnitt zeigt einen Bericht über die Profilerstellungsinformationen an, die während der aus-und weiterbildungsphase Benutzerszenarios aufgezeichnet wurde. Sie können diesen Bericht verwenden, um zu überprüfen, welche Funktionen von der App am meisten aufgerufen und am längsten verwendet wurden. Das Plug-In für die profilgesteuerte Optimierung verwendet die Informationen, um zu bestimmen, welche App-Funktionen hinsichtlich der Geschwindigkeit und welche hinsichtlich der Größe optimiert werden sollten. Das Plug-In konfiguriert Buildoptimierungen, um die kleinste und schnellste App für die Benutzerszenarios zu erstellen, die Sie während der Aus- und Weiterbildung aufgezeichnet haben.

![PGO-Analyseseite](../../build/reference/media/pgofig5analyze.png "PGOFig5Analyze")

Wenn die Schulung der erwarteten Profilerstellungsinformationen erfasst wurden, können Sie **Save Changes** , speichern Sie die analysierten Profildaten im Projekt, um zukünftige Builds zu optimieren. Um die Profildaten zu verwerfen und das Training von Anfang beginnen, wählen Sie **Redo Training**.

Die Profildatendatei wird gespeichert, in Ihrem Projekt in einem **PGO-Trainingsdaten** Ordner. Diese Daten werden verwendet, um die Buildoptimierungseinstellungen des Compilers in der App zu steuern.

![PGO-Datendatei im Projektmappen-Explorer](../../build/reference/media/pgofig6data.png "PGOFig6Data")

Nach der Analyse stellt das Plug-In die Buildoptionen in Ihrem Projekt so ein, dass die Profildaten verwendet werden, um die App während der Kompilierung selektiv zu optimieren. Sie können die App auch weiterhin mit denselben Profildaten ändern und erstellen. Wenn die App erstellt wird, zeigen die Buildausgabeberichte, wie viele Funktionen und Anweisungen anhand der Profildaten optimiert wurden.

![PGO-Ausgabe Diagnose](../../build/reference/media/pgofig7diagnostics.png "PGOFig7Diagnostics")

Wenn Sie während der Entwicklung bedeutende Codeänderungen vornehmen, müssen Sie das Training für die App unter Umständen wiederholen, um eine bestmögliche Optimierung zu erhalten. Es wird empfohlen, das Training für die App zu wiederholen, wenn die Buildausgabeberichte besagen, dass weniger als 80 Prozent Funktionen oder Anweisungen anhand der Profildaten optimiert wurden.