---
title: Installieren der C++-Unterstützung in Visual Studio
description: Visual Studio-Unterstützung für Visual Studio installierenC++
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: a20a2432cbf8c4dc5f211f6f483c0084888f1199
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857163"
---
# <a name="install-c-support-in-visual-studio"></a>Installieren der C++-Unterstützung in Visual Studio

Wenn Sie Visual Studio und die Visual C++-Tools noch nicht heruntergeladen und installiert haben, finden Sie hier Informationen zu den ersten Schritten.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019-Installation

Willkommen bei Visual Studio 2019. Sie können ganz einfach die Features, die Sie benötigen, auswählen und installieren. Aufgrund des dadurch reduzierten Speicherbedarfs, werden diese schnell installiert, während das System weniger beeinträchtigt wird.

> [!NOTE]
> Dieses Thema bezieht sich auf die Installation von Visual Studio unter Windows. [Visual Studio Code](https://code.visualstudio.com/) ist eine vereinfachte, plattformübergreifende Entwicklungsumgebung, die auf Windows-, Mac-und Linux-Systemen ausgeführt wird. Die Microsoft [C/C++ for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) -Erweiterung unterstützt IntelliSense, Debugging, Codeformatierung und automatische Codevervollständigung. Visual Studio für Mac unterstützt Microsoft C++ nicht, unterstützt aber .NET-Sprachen und  eine plattformübergreifende Entwicklung. Installationsanweisungen finden Sie unter [Install Visual Studio für Mac](/visualstudio/mac/installation/).

Sie möchten mehr zu weiteren Neuerungen in dieser Version wissen? Weitere Informationen finden Sie in den Versions [Anmerkungen](/visualstudio/releases/2019/release-notes/)zu Visual Studio.

Bereit für die Installation? Schauen Sie sich diese Schritt-für-Schritt Anleitung an.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>Schritt 1: Stellen Sie sicher, dass Ihr Computer für Visual Studio bereit ist

Vor der Installation von Visual Studio:

1. Informieren Sie sich über die [Systemanforderungen](/visualstudio/releases/2019/system-requirements). Anhand dieser Anforderungen können Sie feststellen, ob Ihr Computer Visual Studio 2019 unterstützt.

1. Laden Sie die aktuellsten Windows-Updates herunter. So stellen Sie sicher, dass Ihr Computer sowohl die neuesten Sicherheitsupdates als auch die erforderlichen Systemkomponenten für Visual Studio besitzt.

1. Starten Sie den Computer neu. Dadurch wird sichergestellt, dass keine ausstehenden Installationen oder Updates die Installation von Visual Studio behindern.

1. Geben Sie Speicherplatz frei. Entfernen Sie nicht benötigte Dateien und Anwendungen z.B. mit der Datenträgerbereinigung-App von Ihrem %Systemlaufwerk%.

Informationen zur parallelen Ausführung vorheriger Versionen von Visual Studio und Visual Studio 2019 finden Sie auf der Seite [Visual Studio 2019 – Zielplattformen und Kompatibilität](/visualstudio/releases/2019/compatibility/).

### <a name="step-2---download-visual-studio"></a>Schritt 2: Herunterladen von Visual Studio

Laden Sie danach die Visual Studio-Bootstrapperdatei herunter. Klicken Sie zu diesem Zweck auf die folgende Schaltfläche, wählen Sie die gewünschte Edition von Visual Studio aus, und klicken Sie dann auf **Speichern** und **Ordner öffnen**.

 > [!div class="button"]
 > [Herunterladen von Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>Schritt 3: Installieren des Visual Studio-Installers

Führen Sie die Bootstrapperdatei aus, um den Visual Studio-Installer zu installieren. Dieses neue, schlanke Installationsprogramm enthält alle Elemente, die Sie zum Installieren und Anpassen von Visual Studio benötigen.

1. Doppelklicken Sie in Ihrem Ordner **Downloads** auf die Bootstrapperdatei, die einer der folgenden Dateien entspricht oder ähnelt:

   * **vs_community.exe** für Visual Studio Community
   * **vs_professional.exe** für Visual Studio Professional
   * **vs_enterprise.exe** für Visual Studio Enterprise

   Wenn eine Benachrichtigung der Benutzerkontensteuerung angezeigt wird, klicken Sie auf **Ja**.

1. Sie werden gebeten, die Microsoft-[Lizenzbedingungen](https://visualstudio.microsoft.com/license-terms/) und die Microsoft-[Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement) zu akzeptieren. Klicken Sie auf **Weiter**.

### <a name="step-4---choose-workloads"></a>Schritt 4: Auswählen von Workloads

Nachdem das Installationsprogramm installiert wurde, können Sie es verwenden, um die Installation anzupassen, indem Sie die gewünschten *Workloads* oder Funktionsgruppen auswählen. Gehen Sie folgendermaßen vor:

1. Suchen Sie die gewünschten Workloads im Bildschirm **Visual Studio wird installiert**.

   ![Visual Studio 2019: Installieren einer Workload](../get-started/media/vs-installer-workloads.png)

   Für den grundlegenden C++-Support wählen Sie die Workload "Desktop Entwicklung mit C++" aus. Sie wird mit dem standardmäßigen Kern-Editor bereitgestellt, der die grundlegende Codebearbeitung für über 20 Sprachen, die Möglichkeit, Code aus einem beliebigen Ordner heraus zu öffnen und zu bearbeiten, ohne dass ein Projekt erforderlich ist, und die integrierte Quellcodekontrolle unterstützt.

   Weitere Workloads unterstützen andere Arten der Entwicklung mit C++. Wählen Sie beispielsweise die Workload "Entwicklung für die universelle Windows-Plattform" aus, um Apps zu erstellen, die die Windows-Runtime des Microsoft Stores verwenden. Wählen Sie "Spieleentwicklung mit C++", um Spiele zu erstellen, die DirectX, Unreal und Cocos2d verwenden. Wählen Sie "Linux Entwicklung mit C++" für Linux-Plattformen aus, einschließlich der Entwicklung im IoT-Bereich.

   Im Bereich **Installationsdetails** werden die enthaltenen und optionalen Komponenten aufgelistet, die von den einzelnen Workloads installiert werden. Sie können optionale Komponenten in dieser Liste auswählen bzw. deaktivieren. Wenn Sie z. b. die Entwicklung mithilfe der Compiler-Tools von Visual Studio 2017 oder 2015 unterstützen möchten, wählen Sie die optionalen MSVC-v141-oder MSVC V140-Komponenten aus. Sie können MFC-Unterstützung, die experimentelle Spracherweiterung für experimentelle Module, IncrediBuild und vieles mehr hinzufügen.

1. Nachdem Sie die gewünschten Workloads und optionalen Komponenten ausgewählt haben, wählen Sie **Installieren**aus.

    Als Nächstes werden Statusbildschirme angezeigt, die über den Fortschritt der Installation von Visual Studio informieren.

> [!TIP]
> Nach der Installation können Sie jederzeit die Installation von Workloads oder Komponenten nachholen. Wenn Sie Visual Studio geöffnet haben, navigieren Sie zu **Extras** > **Tools und Features abrufen…** . Dadurch wird der Visual Studio-Installer geöffnet. Alternativ kann der **Visual Studio-Installer** auch über das Startmenü geöffnet werden. Nun können Sie die Workloads oder Komponenten auswählen, die Sie installieren möchten. Klicken Sie anschließend auf **Ändern**.

### <a name="step-5---choose-individual-components-optional"></a>Schritt 5: Auswählen einzelner Komponenten (optional)

Wenn Sie die Funktion "Workloads" nicht zur Anpassung Ihrer Visual Studio-Installation verwenden möchten, oder wenn Sie weitere Komponenten hinzufügen möchten, als bei einer Workload installiert werden, können Sie dazu einzelne Komponenten auf der Registerkarte " **einzelne Komponenten** " installieren oder hinzufügen. Wählen Sie das gewünschte Element aus, und befolgen Sie dann die weiteren Anweisungen.

  ![Installieren einzelner Komponenten von Visual Studio 2019](../get-started/media/vs-installer-individual-components.png "Installieren von einzelnen Komponenten von Visual Studio")

### <a name="step-6---install-language-packs-optional"></a>Schritt 6: Installieren von Language Packs (optional)

Standardmäßig versucht das Installationsprogramm bei der ersten Ausführung die Sprache des Betriebssystems zu verwenden. Zum Installieren von Visual Studio in einer Sprache Ihrer Wahl klicken Sie im Visual Studio-Installer auf die Registerkarte **Sprachpakete**, und folgen Sie dann den Anweisungen.

  ![Visual Studio 2019-Sprachpakete installieren](../get-started/media/vs-installer-language-packs.png "Installieren von Visual Studio Language Packs")

#### <a name="change-the-installer-language-from-the-command-line"></a>Ändern der Installersprache über die Befehlszeile

Eine andere Möglichkeit zum Ändern der Standardsprache ist die Ausführung des Installers über die Befehlszeile. Mit dem Befehl `vs_installer.exe --locale en-US` können Sie z.B. erzwingen, dass das Installationsprogramm auf Englisch ausgeführt wird. Das Installationsprogramm speichert diese Einstellung, wenn es das nächste Mal ausgeführt wird. Der Installer unterstützt die folgenden Sprachen: zh-CN, zh-TW, cs-CZ, en-US, es-ES, fr-FR, de-DE, it-IT, ja-JP, ko-KR, pl-PL, pt-BR, ru-RU und tr-TR.

### <a name="step-7---change-the-installation-location-optional"></a>Schritt 7: Ändern des Installationspfads (optional)

Sie können den Speicherbedarf für die Installation von Visual Studio auf Ihrem Systemlaufwerk reduzieren. Sie können den Downloadcache, freigegebene Komponenten, SDKs und Tools auf andere Datenträger verschieben, und Visual Studio dort belassen, wo es am schnellsten ausgeführt werden kann.

  ![Visual Studio 2019-Installations Speicherorte ändern](../get-started/media/vs-installer-installation-locations.png "Ändern des Installations Speicher Orts")

> [!IMPORTANT]
> Sie können nur bei der ersten Installation von Visual Studio ein anderes Laufwerk auswählen. Wenn Sie Visual Studio bereits installiert haben und das Laufwerk wechseln möchten, müssen Sie Visual Studio deinstallieren und anschließend neu installieren.

### <a name="step-8---start-developing"></a>Schritt 8: Mit dem Entwickeln beginnen

1. Klicken Sie nach Abschluss der Visual Studio-Installation auf **Starten**, um mit dem Programmieren in Visual Studio zu beginnen.

1. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

1. Geben Sie den Typ der zu programmierenden App im Suchfeld ein, um eine Liste der verfügbaren Vorlagen anzuzeigen. Die Liste der Vorlagen basiert auf den Workloads, die Sie bei der Installation ausgewählt haben. Wählen Sie andere Workloads aus, um andere Vorlagen anzuzeigen.

   Sie können die Suchergebnisse nach bestimmten Programmiersprachen filtern, indem Sie die Dropdownliste **Sprache** verwenden. Sie können außerdem die Listen **Plattform** und **Projekttyp** zum Filtern verwenden.

1. Ihr neues Projekt wird dann in Visual Studio geöffnet, und Sie können damit anfangen, Code zu schreiben.

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017-Installation

In Visual Studio 2017 ist es einfach, nur die Features auszuwählen und zu installieren, die Sie benötigen. Aufgrund des dadurch reduzierten Speicherbedarfs, werden diese schnell installiert, während das System weniger beeinträchtigt wird.

### <a name="prerequisites"></a>Erforderliche Voraussetzungen

- Eine Breitband-Internetverbindung. Der Visual Studio-Installer kann mehrere Gigabyte an Daten herunterladen.

- Ein Computer, auf dem Microsoft Windows 7 oder eine höhere Version ausgeführt wird. Für ein optimales Entwicklungserlebnis empfehlen wir Windows 10. Stellen Sie sicher, dass die neuesten Updates auf das System angewendet werden, bevor Sie Visual Studio installieren.

- Ausreichend freier Speicherplatz. Visual Studio benötigt mindestens 7 GB Speicherplatz und kann 50 GB oder mehr belegen, wenn viele gängige Optionen installiert sind. Es wird empfohlen, dass Sie Sie auf Laufwerk C: installieren.

Ausführliche Informationen zu Speicherplatz und Betriebssystemanforderungen finden Sie unter [Systemanforderungen der Visual Studio-Produktfamilie](/visualstudio/productinfo/vs2017-system-requirements-vs). Das Installationsprogramm meldet, wie viel Speicherplatz für die ausgewählten Optionen erforderlich ist.

### <a name="download-and-install"></a>Zur Installation herunterladen können Sie

1. Laden Sie den neuesten Visual Studio 2017-Installer für Windows herunter.

   > [!div class="nextstepaction"]
   > [Installieren von Visual Studio 2017 Community](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Die Community Edition eignet sich für einzelne Entwickler, Schulungsumgebungen, akademische Forschung und Open Source-Entwicklung. Installieren Sie für andere Verwendungen [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) oder [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

1. Suchen Sie die heruntergeladene Installer-Datei, und führen Sie Sie aus. Sie wird möglicherweise in Ihrem Browser angezeigt, oder Sie finden Sie möglicherweise im Ordner "Downloads". Der Installer benötigt Administrator Rechte, um ausgeführt werden zu können. Möglicherweise wird ein Dialogfeld " **Benutzerkontensteuerung** " angezeigt, in dem Sie aufgefordert werden, die Berechtigung zu erteilen, dass das Installationsprogramm Änderungen am System vornehmen Wählen Sie **Ja**aus. Wenn Sie Probleme haben, suchen Sie die heruntergeladene Datei im Datei-Explorer, klicken Sie mit der rechten Maustaste auf das Installer-Symbol, und wählen Sie im Kontextmenü die Option **als Administrator ausführen** aus.

   ![Herunterladen und Installieren des Visual Studio-Installers](media/vscpp-concierge-run-installer.gif "Herunterladen und Installieren des Visual Studio-Installer")

1. Der Installer bietet Ihnen eine Liste von Workloads, bei denen es sich um Gruppen von verwandten Optionen für bestimmte Entwicklungsbereiche handelt. Die unter C++ Stützung für ist nun Teil der optionalen Workloads, die nicht standardmäßig installiert werden.

   !["Desktop-Entwicklung mit C++" Workload](media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

   Wählen C++Sie für die **Desktop Entwicklung mit C++**  Arbeitsauslastung aus, und klicken Sie dann auf **Installieren**.

   ![Installieren der Desktop Entwicklung mit C++ Arbeitsauslastung](media/vscpp-concierge-choose-workload.gif "Installieren der Desktop Entwicklung mit C++ Arbeitsauslastung")

1. Wenn die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **starten** , um Visual Studio zu starten.

   Wenn Sie Visual Studio zum ersten Mal ausführen, werden Sie aufgefordert, sich mit einem Microsoft-Konto anzumelden. Wenn Sie über keins verfügen, können Sie es kostenloses erstellen. Sie müssen auch ein Design auswählen. Keine Sorge, Sie können Sie später ändern, wenn Sie möchten.

   Visual Studio kann einige Minuten dauern, bis die Anwendung zum ersten Mal ausgeführt wird. So sieht es in einem kurzen Zeitraum aus:

   ![Visual Studio 2017-Anmeldung](media/vscpp-quickstart-first-run.gif "Visual Studio 2017-Anmeldung")

   Visual Studio startet viel schneller, wenn Sie es erneut ausführen.

1. Wenn Visual Studio geöffnet wird, überprüfen Sie, ob das Flag-Symbol in der Titelleiste hervorgehoben ist:

   ![Benachrichtigungs Kennzeichen für Visual Studio 2017](media/vscpp-first-start-page-flag.png "Benachrichtigungs Kennzeichen für Visual Studio 2017")

   Wenn es hervorgehoben ist, wählen Sie es aus, um das **Benachrichtigungs**-Fenster zu öffnen. Wenn für Visual Studio Updates verfügbar sind, empfiehlt es sich, diese jetzt zu installieren. Starten Sie Visual Studio nach Abschluss der Installation neu.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015-Installation

Auf der Seite [Downloads älterer Versionen von Visual Studio](https://www.visualstudio.com/vs/older-downloads/) können Sie Visual Studio 2015 herunterladen. Führen Sie das Setupprogramm aus, klicken Sie auf **Benutzerdefinierte Installation**, und wählen Sie die C++-Komponente aus. Wenn Sie C++ einer vorhandenen Visual Studio 2015-Installation Unterstützung hinzufügen möchten, klicken Sie auf die Windows-Schaltfläche "Start", **und geben Sie**"Software Öffnen Sie das Programm in der Ergebnisliste, und suchen Sie die Visual Studio 2015-Installation in der Liste der installierten Programme. Doppelklicken Sie darauf, und wählen Sie dann **ändern** aus, C++ und wählen Sie die zu installierendes Visualisierung aus.

In der Regel wird die Verwendung von Visual Studio 2017 empfohlen, auch wenn Sie dann Ihren Code mithilfe des Visual Studio 2015-Compilers kompilieren müssen. Weitere Informationen finden Sie unter [Use native multi-targeting in Visual Studio to build old projects (Verwenden der nativen Festlegung von Zielversionen in Visual Studio, um alte Projekte zu erstellen)](../porting/use-native-multi-targeting.md).

::: moniker-end

Wenn Visual Studio ausgeführt wird, können Sie mit dem nächsten Schritt fortfahren.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erstellen eines C++ Projekts](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
