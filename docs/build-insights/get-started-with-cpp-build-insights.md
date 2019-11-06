---
title: Einstieg in C++ Build Insights
description: Eine allgemeine Übersicht über die Verwendung der Tools zur Leistungsanalyse zur Erstellung von Builds, die Teil von C++ builderkenntnissen sind.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c31d317cd7b9c6465362e3e532db2128303f602
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73633225"
---
# <a name="get-started-with-c-build-insights"></a>Einstieg in C++ Build Insights

::: moniker range="<=vs-2017"

Die C++ Build Insights-Tools sind in Visual Studio 2019 verfügbar. Um die Dokumentation für diese Version anzuzeigen, legen Sie das Steuerelement für die Visual Studio-Versions Auswahl für diesen Artikel auf Visual Studio 2019 fest.

::: moniker-end
::: moniker range="vs-2019"

C++Build Insights ist eine Sammlung von Tools, die eine bessere Sichtbarkeit der Microsoft C++ Visual (MSVC)-Toolkette bereitstellt. Die Tools erfassen Daten zu Ihren C++ Builds und stellen Sie in einem Format dar, das Ihnen helfen kann, häufig gestellte Fragen zu beantworten, wie z. b.:

- Werden meine Builds ausreichend parallelisiert?
- Was sollte ich in meinen vorkompilierten Header (PCH) einschließen?
- Gibt es einen bestimmten Engpass, auf den ich mich konzentrieren sollte, um meine buildgeschwindigkeiten zu steigern?

Die zwei Hauptkomponenten dieser Technologie sind das Befehlszeilen-Hilfsprogramm " *vcperf. exe* " und ein Add-in für den Windows Performance Analyzer (WPA) Trace Viewer. Das Hilfsprogramm wird verwendet, um Ablauf Verfolgungen Ihres Builds zu erfassen, während das Add-in Sie in WPA anzeigen können. Führen Sie diese Schritte aus, um die ersten Schritte mit diesen beiden Tools auszuführen.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>Schritt 1: Installieren und Konfigurieren von Windows Performance Analyzer

WPA ist ein Trace Viewer, der im Windows Assessment and Deployment Kit (ADK) verfügbar ist. Dabei handelt es sich um ein separates Hilfsprogramm, das nicht Teil der Komponenten ist, die Sie mit dem Visual Studio-Installer installieren können.

Eine Version von WPA, die C++ Build Insights unterstützt, ist zurzeit nur in der Windows ADK Insider Preview verfügbar. Für den Zugriff auf diese Vorschauversion müssen Sie sich für das [Windows Insider-Programm](https://insider.windows.com)registrieren. Sie müssen nicht das Windows 10 Insider Preview-Betriebssystem installieren, um die Windows ADK-Vorschau zu erhalten. Sie müssen Ihre Microsoft-Konto nur beim Windows Insider-Programm registrieren.

### <a name="to-download-and-install-wpa"></a>So können Sie WPA herunterladen und installieren

1. Navigieren [Sie zur Downloadseite](https://www.microsoft.com/software-download/windowsinsiderpreviewADK)für Windows ADK Insider Preview.

1. Laden Sie die Windows ADK Insider Preview herunter. Dabei handelt es sich um ein Datenträger Image.

1. Öffnen Sie das Datenträger Image, und führen Sie das Installationsprogramm *adksetup. exe* aus.

1. Wenn Sie zur Eingabe der zu installierenden Funktionen aufgefordert werden, wählen Sie das **Windows Performance Toolkit**aus. Wenn Sie möchten, können Sie andere Features auswählen, aber Sie müssen nicht WPA installieren.

   ![Der Bildschirm zur Funktionsauswahl des Windows Performance Analyzer-Installers](media/wpa-installation.png)

### <a name="configuration-steps"></a>So konfigurieren Sie Build Insights

1. Starten Sie WPA.

1. Wählen Sie **Fenster** aus, > **Tabellen auswählen (experimentell)** .

1. Scrollen Sie nach unten zum Abschnitt **Diagnose** .

1. Wählen Sie alle MSVC-Ansichten zum Erstellen von Erkenntnissen aus.

   ![Tabellen Auswahlbereich von Windows Performance Analyzer](media/wpa-configuration.png)

## <a name="step-2-trace-your-build-with-vcperfexe"></a>Schritt 2: Erstellen einer Ablauf Verfolgung für den Build mit "vcperf. exe"

Um buildinsights-Daten anzuzeigen C++ , erfassen Sie Sie zuerst in einer Ablauf Verfolgungs Datei, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie eine systemeigene Tools-oder Cross Tools Developer-Eingabeaufforderung für Visual Studio 2019 im Administrator Modus. (Klicken Sie mit der rechten Maustaste auf das Startmenü Element, und wählen Sie **mehr** > **als Administrator ausführen**.)

1. Geben Sie im Eingabe Aufforderungs Fenster den folgenden Befehl ein:

   **vcperf. exe/Start _Sessionname_**

   Wählen Sie einen Sitzungs Namen aus, den Sie für *Sessionname*merken.

1. Erstellen Sie das Projekt wie gewohnt. Sie müssen nicht das gleiche Eingabe Aufforderungs Fenster verwenden, um zu erstellen.

1. Geben Sie im Eingabe Aufforderungs Fenster den folgenden Befehl ein:

   **vcperf. exe/Stop _Sessionname_ _Tracefile. ETL_**

   Verwenden Sie den gleichen Sitzungs Namen, den Sie zuvor für *Sessionname* ausgewählt haben. Wählen Sie einen geeigneten Namen für die Ablauf Verfolgungs Datei *Tracefile. ETL* aus.

So sieht eine typische *vcperf. exe* -Befehlssequenz in einem Entwickler-Eingabe Aufforderungs Fenster aus:

![Ein einfaches Verwendungs Szenario für "vcperf. exe"](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>Wichtige Hinweise zu "vcperf. exe"

- Administrator Rechte sind erforderlich, um eine *vcperf. exe* -Ablauf Verfolgung zu starten oder zu verhindern. Verwenden Sie ein Developer-Eingabe Aufforderungs Fenster, das Sie öffnen, indem Sie **als Administrator ausführen**verwenden.

- Auf einem Computer kann jeweils nur eine Ablauf Verfolgungs Sitzung ausgeführt werden.

- Achten Sie darauf, den Sitzungs Namen zu merken, den Sie zum Starten der Ablauf Verfolgung verwendet haben. Es kann problematisch sein, eine laufende Sitzung anzuhalten, ohne den Namen zu kennen.

- Ebenso wie " *cl. exe* " und " *Link. exe*" ist das Befehlszeilenprogramm " *vcperf. exe* " in einer MSVC-Installation enthalten. Zum Abrufen dieser Komponente sind keine weiteren Schritte erforderlich.

- *vcperf. exe* sammelt Informationen zu allen MSVC-Tools, die auf Ihrem System ausgeführt werden. Daher müssen Sie den Build nicht von derselben Eingabeaufforderung aus starten, die Sie zum Erfassen der Ablauf Verfolgung verwendet haben. Sie können Ihr Projekt entweder über eine andere Eingabeaufforderung oder sogar in Visual Studio erstellen.

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>Schritt 3: Anzeigen der Ablauf Verfolgung in Windows Performance Analyzer

Starten Sie WPA, und öffnen Sie die soeben gesammelte Ablauf Verfolgung. WPA sollte Sie als eine C++ buildinsights-Ablauf Verfolgung erkennen, und die folgenden Sichten sollten im Panel Graph-Explorer auf der linken Seite angezeigt werden:

- Build Explorer
- Dateien
- Funktion

Wenn diese Sichten nicht angezeigt werden, überprüfen Sie, ob WPA ordnungsgemäß konfiguriert ist, wie in [Schritt 1](#configuration-steps)beschrieben. Sie können die Builddaten anzeigen, indem Sie die Ansichten auf der rechten Seite in das leere Analysefenster ziehen, wie hier gezeigt:

![Anzeigen einer C++ Build Insights-Ablauf Verfolgung in Windows Performance Analyzer](media/wpa-viewing-trace.gif)

Andere Ansichten sind im Diagramm-Explorer-Panel verfügbar. Ziehen Sie diese in das Analysefenster, wenn Sie an den darin enthaltenen Informationen interessiert sind. Ein nützliches Beispiel ist die CPU-Ansicht (Sampling), die die CPU-Auslastung im gesamten Build anzeigt.

## <a name="more-information"></a>Weitere Informationen

[Grundlagen des Windows Performance Analyzer](wpa-basics.md)\
Erfahren Sie mehr über häufige WPA-Vorgänge, mit denen Sie Ihre buildüberwachungen analysieren können.

[vcperf. exe-Referenz](vcperf-reference.md)\
Die Befehlsreferenz *vcperf. exe* listet alle verfügbaren Befehlsoptionen auf.

[Referenz\ zu Windows Performance Analyzer-Sichten](wpa-views-reference.md)
In diesem Artikel finden Sie ausführliche Informationen zu C++ den Build Insights-Sichten in WPA.

[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) -\
Die offizielle WPA-Dokumentations Website.

::: moniker-end
