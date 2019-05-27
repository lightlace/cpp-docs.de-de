---
title: Konfigurieren von Programmen für Windows XP
ms.date: 05/16/2019
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 6c94c6a66d0f22b8707012856a65df4b19965acb
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837137"
---
# <a name="configuring-programs-for-windows-xp"></a>Konfigurieren von Programmen für Windows XP

Da Visual Studio mehrere Plattformtoolsets unterstützt, können Sie Betriebssysteme und Laufzeitbibliotheken als Ziel festlegen, die vom Standardtoolset nicht unterstützt werden. Beispielsweise können Sie durch Wechseln des Plattformtoolsets die vom MSVC-Compiler in Visual Studio unterstützten C++11-, C++14- und C++17-Spracherweiterungen verwenden, um Apps für die Zielplattformen Windows XP und Windows Server 2003 zu erstellen. Sie können auch ältere Plattformtoolsets verwenden, um binärkompatiblen Legacycode zu verwalten und dennoch die neuesten Funktionen der Visual Studio-IDE zu nutzen.

Visual Studio 2019 und höher umfasst keine Unterstützung für das Erstellen von Code für Windows XP mithilfe des v142-Toolsets. Unterstützung für die Windows XP-Entwicklung unter Verwendung des Toolsets v141, das zum Lieferumfang von Visual Studio 2017 gehörte, ist als optionale Komponente im Visual Studio-Installer verfügbar.

## <a name="install-the-windows-xp-platform-toolset"></a>Installieren des Windows XP-Plattformtoolsets

Um das Plattformtoolset und die Komponenten abzurufen, die für die Zielplattformen Windows XP und Windows Server 2003 erforderlich sind, führen Sie in Visual Studio 2017 den Visual Studio-Installer aus. Achten Sie bei der erstmaligen Installation von Visual Studio oder beim Auswählen von **Ändern**, um eine bestehende Installation zu ändern, darauf, dass die Workload **Desktopentwicklung mit C++** ausgewählt ist. Wählen Sie in der Liste der optionalen Komponenten für diese Workload **Windows XP-Unterstützung für C++** und dann **Installieren** oder **Ändern** aus.

## <a name="windows-xp-targeting-experience"></a>Windows XP als Ziel

Das in Visual Studio enthaltene Windows XP-Plattformtoolset ist eine Version des Windows 7-SDK, es verwendet jedoch den aktuellen C++-Compiler. Es konfiguriert außerdem Projekteigenschaften auf entsprechende Standardwerte, beispielsweise durch Angabe eines mit älteren Zielplattformen kompatiblen Linkers. Nur Windows Desktop-Apps, die unter Verwendung eines Windows XP-Plattformtoolsets erstellt werden, können unter Windows XP und Windows Server 2003 ausgeführt werden; diese Apps können jedoch auch unter neueren Windows-Betriebssystemen ausgeführt werden.

#### <a name="to-target-windows-xp"></a>So entwickeln Sie für Windows XP

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.

1. Legen Sie im Dialogfeld **Eigenschaftenseiten** für das Projekt unter **Konfigurationseigenschaften** > **Allgemein** die Eigenschaft **Platform Toolset** auf das gewünschte Windows XP-Toolset fest. Wählen Sie beispielsweise **Visual Studio 2017 – Windows XP (v141_xp)** aus, um Code für Windows XP und Windows Server 2003 mithilfe des Microsoft C++-Compilers in Visual Studio 2017 zu erstellen.

### <a name="c-runtime-support"></a>C++-Laufzeitunterstützung

Neben dem Windows XP-Plattformtoolset bieten die C-Laufzeitbibliothek (CRT), die C++-Standardbibliothek, die Active Template Library (ATL), die Concurrency Runtime-Bibliothek (ConCRT), die Parallel Patterns Library (PPL), die Microsoft Foundation Class-Bibliothek (MFC) und die C++ AMP-Bibliothek (C++ Accelerated Massive Programming) Laufzeitunterstützung für Windows XP und Windows Server 2003. Für diese Betriebssysteme sind die unterstützten Mindestversionen Windows XP Service Pack 3 (SP3) für x86, Windows XP Service Pack 2 (SP2) für x64 und Windows Server 2003 Service Pack 2 (SP2) sowohl für x86 als auch für x64.

Diese Bibliotheken werden von den von Visual Studio installierten Plattformtoolsets unterstützt, abhängig vom Ziel:

|Bibliothek|Standard-Plattformtoolset mit Windows-Desktop-Apps als Ziel|Standard-Plattformtoolset mit Store-Apps als Ziel|Windows XP-Plattformtoolset mit Windows XP, Windows Server 2003 als Ziel|
|---|---|---|---|
|CRT|X|X|X|
|C++-Standardbibliothek|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> Apps, die in C++/CLI geschrieben sind und .NET Framework 4 als Ziel haben, können unter Windows XP und Windows Server 2003 ausgeführt werden.

### <a name="differences-between-the-toolsets"></a>Unterschiede zwischen den Toolsets

Aufgrund von Unterschieden bei Plattform- und Bibliotheksunterstützung ist die Entwicklungsumgebung für Apps, die ein Windows XP-Plattformtoolset verwenden, nicht so umfassend wie für Apps, die das standardmäßige Visual Studio-Plattformtoolset verwenden.

- **Funktionen der Programmiersprache C++**

   In Apps, die das v110\_xp-Plattformtoolset verwenden, werden nur die Funktionen der Programmiersprache C++unterstützt, die in Visual Studio 2012 implementiert sind. In Apps, die das v120\_xp-Plattformtoolset verwenden, werden nur die Funktionen der Programmiersprache C++unterstützt, die in Visual Studio 2013 implementiert sind. In Apps, die das v140\_xp-Plattformtoolset verwenden, werden nur die Funktionen der Programmiersprache C++unterstützt, die in Visual Studio 2015 implementiert sind. Visual Studio verwendet für Builds mit den älteren Plattformtoolsets den entsprechenden Compiler. Verwenden Sie das neueste Windows XP-Plattformtoolset, um weitere C++-Features zu nutzen, die in dieser Version des Compilers implementiert sind.

- **Remotedebuggen**

   Die Remotetools für Visual Studio unterstützen kein Remotedebuggen unter Windows XP oder Windows Server 2003. Zum Debuggen einer App, die unter Windows XP oder Windows Server 2003 ausgeführt wird, können Sie einen Debugger aus einer älteren Version von Visual Studio verwenden, um diese lokal oder remote zu debuggen. Dies ähnelt dem Debuggen einer Anwendung unter Windows Vista, das ein Laufzeitziel des Plattformtoolsets, aber kein Remotedebuggingziel ist.

- **Statische Analyse**

   Die Windows XP-Plattformtoolsets unterstützen keine statischen Analysen, da die SAL-Anmerkungen für das Windows 7-SDK und die Laufzeitbibliotheken nicht kompatibel sind. Wenn Sie statische Analysen für eine App durchführen möchten, die Windows XP oder Windows Server 2003 unterstützt, können sie vorübergehend die Projektmappe so umschalten, dass sie zum Durchführen der Analyse das Standard-Plattformtoolset als Ziel verwendet, und dann zum Windows XP-Plattformtoolset zurückwechseln, um die App zu erstellen.

- **Debuggen von DirectX-Grafiken**

   Da der Grafikdebugger die Direct3D 9-API nicht unterstützt, kann sie nicht zum Debuggen von Apps verwendet werden, die Direct3D unter Windows XP oder Windows Server 2003 verwenden. Wenn die App jedoch einen alternative Renderer implementiert, der die Direct3D 10- oder Direct3D 11-API verwendet, kann der Grafikdebugger verwendet werden, um Probleme mit der Verwendung dieser APIs zu diagnostizieren.

- **Erstellen von HLSL**

   Standardmäßig kompiliert das Windows XP-Toolset keine HLSL-Quellcodedateien. Zur Kompilierung von HLSL-Dateien laden Sie das June 2010 DirectX SDK herunter und installieren es und legen dann die VC-Verzeichnisse des Projekts so fest, dass es eingeschlossen ist. Weitere Informationen finden Sie im Abschnitt „DirectX-SDK registriert keine Include/Library-Pfade bei Visual Studio 2010“ der [June 2010 DirectX SDK-Downloadseite](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).
