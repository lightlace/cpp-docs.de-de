---
title: Konfigurieren von Programmen für Windows XP
ms.date: 02/02/2018
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 989a4e2c7e91c05498902bf1c5cb9d838ee47c3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273801"
---
# <a name="configuring-programs-for-windows-xp"></a>Konfigurieren von Programmen für Windows XP

Da Visual Studio mehrere Plattformtoolsets unterstützt, können Sie abzielen, Betriebssysteme und Laufzeitbibliotheken, die die vom Standardtoolset nicht unterstützt werden. Beispielsweise durch den Wechsel des Plattformtoolsets, können Sie die C ++ 11, C ++ 14 und C ++ 17 sprachverbesserungen, die von der MSVC-Compiler in Visual Studio unterstützt werden zum Erstellen von apps, die auf Windows XP und Windows Server 2003 ausgerichtet. Sie können auch ältere Plattformtoolsets verwenden, um binärkompatiblen Legacycode zu verwalten und dennoch von den neuesten Features von Visual Studio-IDE profitieren.

## <a name="install-the-windows-xp-platform-toolset"></a>Installieren Sie das Windows XP-Plattformtoolset

Führen Sie Visual Studio-Installer aus, um die Plattformtoolset und das Ziel Windows XP und Windows Server 2003-Komponenten in Visual Studio 2017 abzurufen. Wenn Sie Visual Studio zum ersten Mal installieren, oder bei der Auswahl **ändern** zum Ändern einer vorhandenen Installations sicher, dass die **Desktopentwicklung mit C++** Workload ausgewählt ist. Wählen Sie in der Liste der optionalen Komponenten für diese Workload **Windows XP-Unterstützung für C++**, und wählen Sie dann **installieren** oder **ändern**.

## <a name="windows-xp-targeting-experience"></a>Windows XP als Ziel

Der Windows XP-Plattformtoolset, das in Visual Studio enthalten ist, ist eine Version von Windows 7 SDK den aktuellen C++-Compiler verwendet. Es konfiguriert außerdem Projekteigenschaften auf entsprechende Standardwerte, z. B. die Spezifikation eines kompatiblen Linkers kompatibel für die zielfestlegung auf Elementebene. Nur Windows-desktop-apps, die erstellt werden, mithilfe einer Windows XP-Plattformtoolset, die auf Windows XP und Windows Server 2003 ausgeführt wird, aber diese apps können auch auf neueren Windows-Betriebssysteme ausführen.

#### <a name="to-target-windows-xp"></a>So entwickeln Sie für Windows XP

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.

1. In der **Eigenschaftenseiten** Dialogfeld für das Projekt unter **Konfigurationseigenschaften** > **allgemeine**legen die **-Plattformtoolset** Eigenschaft, um das gewünschte Windows XP-Toolset. Wählen Sie z. B. **Visual Studio 2017 – Windows XP (v141_xp)** zum Erstellen von Code für Windows XP und Windows Server 2003, mithilfe von Microsoft Visual C++ 2017-Compiler.

### <a name="c-runtime-support"></a>C++-Laufzeitunterstützung

Zusammen mit dem Windows XP-Plattformtoolset, die C-Laufzeitbibliothek (CRT), C++-Standardbibliothek, Active Template Library (ATL), Concurrency Runtime-Bibliothek (ConCRT), Parallel Patterns Library (PPL), Microsoft Foundation Class-Bibliothek (MFC) und C++ AMP (C++- Accelerated Massive Programming) Bibliothek enthalten die Common Language runtimeunterstützung für Windows XP und Windows Server 2003. Für diese Betriebssysteme sind die minimalen unterstützten Versionen für Windows XP Service Pack 3 (SP3) für X86, Windows XP Service Pack 2 (SP2) für X64 und Windows Server 2003 Service Pack 2 (SP2) für x X86 und X64.

Diese Bibliotheken werden von den Plattformtoolsets von Visual Studio, installiert werden, je nach dem Ziel unterstützt:

|Bibliothek|Standard-Plattformtoolset mit Windows-Desktop-Apps als Ziel|Standard-Plattform Toolset für Store-apps|Windows XP-Plattformtoolset, die für Windows XP, Windows Server 2003|
|---|---|---|---|
|CRT|X|X|X|
|C++-Standardbibliothek|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> Apps, die in C++ geschrieben sind c++ / CLI und der Zielversion .NET Framework 4 auf Windows XP und Windows Server 2003 ausgeführt werden.

### <a name="differences-between-the-toolsets"></a>Unterschiede zwischen den Toolsets

Aufgrund von Unterschieden bei Plattform-und bibliotheksunterstützung ist die Entwicklungsumgebung für apps, die ein Windows XP-Plattformtoolset verwenden werden, nicht so umfassend wie bei apps, die das standardmäßige Visual Studio-Plattformtoolset verwenden.

- **Funktionen der Programmiersprache C++**

   Nur C++-Sprachfeatures in Visual Studio 2012 implementiert werden in apps, die die v110 verwenden unterstützt\_Xp-Plattformtoolset. Nur C++-Sprachfeatures in Visual Studio 2013 implementiert werden in apps, die die v120 verwenden unterstützt\_Xp-Plattformtoolset. Nur C++-Sprachfeatures in Visual Studio 2015 implementiert werden in apps, die die v140 verwenden unterstützt\_Xp-Plattformtoolset. Visual Studio verwendet den entsprechenden Compiler bei der Erstellung der älteren Plattformtoolsets. Verwenden Sie das neueste Windows XP-Plattformtoolset, um zusätzliche Funktionen der Programmiersprache C++ implementiert, die in dieser Version des Compilers nutzen.

- **Remotedebuggen**

   Remotetools für Visual Studio unterstützt das Remotedebuggen auf Windows XP oder Windows Server 2003 nicht. Um eine app Debuggen, wenn es auf Windows XP oder Windows Server 2003 ausgeführt wird, können Sie einen Debugger aus einer älteren Version von Visual Studio verwenden, um lokal oder Remote zu debuggen. Dies ähnelt dem Debuggen einer Anwendung unter Windows Vista, das ein Laufzeitziel des Plattformtoolsets, aber kein Remotedebuggingziel ist.

- **Statische Analyse**

   Die Windows XP-Plattformtoolsets unterstützen keine statischen Analyse, da die SAL-Anmerkungen für das Windows 7-SDK und die Laufzeitbibliotheken nicht kompatibel sind. Bei statischen Analyse für eine app durchführen, die von Windows XP oder Windows Server 2003 unterstützt werden sollen, können Sie vorübergehend die Projektmappe, um die Standard-Plattformtoolset zum Durchführen der Analyse als Ziel zu wechseln und wechseln Sie dann zu dem Windows XP-Plattformtoolset zum Erstellen die app.

- **Debuggen von DirectX-Grafiken**

   Da der Grafikdebugger die Direct3D 9-API nicht unterstützt, kann es zum Debuggen von apps, die Direct3D unter Windows XP oder Windows Server 2003 verwenden verwendet werden. Wenn die App jedoch einen alternative Renderer implementiert, der die Direct3D 10- oder Direct3D 11-API verwendet, kann der Grafikdebugger verwendet werden, um Probleme mit der Verwendung dieser APIs zu diagnostizieren.

- **Building HLSL**

   Standardmäßig kompiliert das Windows XP-Toolset keine HLSL-Quellcodedateien. Zur Kompilierung von HLSL-Dateien laden Sie das June 2010 DirectX SDK herunter und installieren es und legen dann die VC-Verzeichnisse des Projekts so fest, dass es eingeschlossen ist. Weitere Informationen finden Sie unter der "DirectX-SDK registriert keine Include/Library-Pfade bei Visual Studio 2010" im Abschnitt der [June 2010 DirectX SDK-Downloadseite](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).
