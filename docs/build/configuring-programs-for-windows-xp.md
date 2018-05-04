---
title: Konfigurieren von Programmen für Windows XP | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a846ea5508173ce0e383b1c4b8798b896ae5be0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Konfigurieren von Programmen für Windows XP

Da Visual Studio mehrere Plattformtoolsets unterstützt, können Sie abzielen, Betriebssysteme und Laufzeitbibliotheken, die die vom Standardtoolset nicht unterstützt werden. Beispielsweise durch den Wechsel des Plattformtoolsets, können C ++ 11 und C ++ 14 C ++ 17-spracherweiterungen unterstützt, die vom Visual C++-Compiler in Visual Studio zum Erstellen von apps, die auf [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Sie können auch ältere Plattformtoolsets verwenden, um binärkompatiblen Legacycode zu verwalten und dennoch die neuesten Funktionen von Visual Studio-IDE nutzen.

## <a name="install-the-windows-xp-platform-toolset"></a>Installieren Sie die Windows XP-Plattformtoolset
Zum Abrufen der Plattformtoolset und Komponenten Ziel [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] führen Sie in Visual Studio 2017 Installer für Visual Studio. Wenn Sie ursprünglich Visual Studio installieren oder wenn Sie die Option **ändern** zum Ändern einer vorhandenen Installations sicher, dass die **Desktopentwicklung mit C++** arbeitsauslastung ausgewählt ist. Wählen Sie in der Liste der optionalen Komponenten, die für diese arbeitsauslastung **Windows XP-Unterstützung für C++**, und wählen Sie dann **installieren** oder **ändern**.

## <a name="windows-xp-targeting-experience"></a>Windows XP als Ziel

Die Windows XP-Plattformtoolset, die in Visual Studio enthalten ist, ist eine Version von den [!INCLUDE[win7](../build/includes/win7_md.md)] SDK, sondern verwendet die aktuellen C++-Compiler. Es konfiguriert außerdem Projekteigenschaften auf entsprechende Standardwerte, z. B. die Spezifikation eines kompatiblen Linkers kompatibel für die zielfestlegung auf Elementebene. Nur Windows desktop-apps, die erstellt werden, ein Windows XP-Plattformtoolset mit weiterlaufen [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], aber diese apps können auch auf neueren Windows-Betriebssysteme ausführen.

#### <a name="to-target-windows-xp"></a>So entwickeln Sie für Windows XP

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.

1. In der **Eigenschaftenseiten** Dialogfeld für das Projekt unter **Konfigurationseigenschaften** > **allgemeine**legen die **Plattformtoolset** Eigenschaft, um das gewünschte Windows XP-Toolset. Wählen Sie z. B. **2017 für Visual Studio - Windows XP (v141_xp)** zum Erstellen von Code für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] mithilfe des Microsoft Visual C++ 2017-Compilers.

### <a name="c-runtime-support"></a>C++-Laufzeitunterstützung

Zusammen mit dem Windows XP-Plattformtoolset, die C-Laufzeitbibliothek (CRT), C++-Standardbibliothek, Active Template Library (ATL), Concurrency Runtime-Bibliothek (ConCRT), Parallel Patterns Library (PPL), Microsoft Foundation Class-Bibliothek (MFC) und C++ AMP (C++- Accelerated Massive Programmierung) Bibliothek enthalten Laufzeitunterstützung für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Für diese Betriebssysteme, die minimalen unterstützten Versionen sind [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 (SP3) für X86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 (SP2) für X64, und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 (SP2) für x X86 und X64.

Diese Bibliotheken werden durch die von Visual Studio installiert ist, abhängig von der Ziel-Plattformtoolsets unterstützt:

|Bibliothek|Standard-Plattformtoolset mit Windows-Desktop-Apps als Ziel|Standard-Plattform Toolset für die Zielgruppenadressierung-Store-apps|Windows XP-Plattformtoolset mit [!INCLUDE[winxp](../build/includes/winxp_md.md)],[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] als Ziel|
|---|---|---|---|
|CRT|X|X|X|
|C++-Standardbibliothek|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> Apps, die in C++/CLI geschrieben sind und .NET Framework 4 als Ziel haben, können unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] ausgeführt werden.

### <a name="differences-between-the-toolsets"></a>Unterschiede zwischen den Toolsets

Aufgrund von Unterschieden bei Plattform-und bibliotheksunterstützung ist ist die Entwicklungsumgebung für apps, die ein Windows XP-Plattformtoolset verwenden, nicht so umfassend wie für apps, die die Standard-Plattformtoolset Visual Studio verwenden.

- **C++-Sprachfunktionen**

   Nur Features der Programmiersprache C++ in Visual Studio 2012 implementiert werden in apps, die die v110 unterstützt\_Xp-Plattformtoolset. Nur Features der Programmiersprache C++ in Visual Studio 2013 implementiert werden in apps, die die v120 unterstützt\_Xp-Plattformtoolset. Nur Features der Programmiersprache C++ in Visual Studio 2015 implementiert werden in apps, die die v140 unterstützt\_Xp-Plattformtoolset. Visual Studio verwendet den entsprechenden Compiler bei der Erstellung der älteren Plattformtoolsets. Verwenden Sie das neueste Windows XP-Plattformtoolset, um zusätzliche Funktionen der Programmiersprache C++ in dieser Version des Compilers implementiert nutzen.

- **Remotedebuggen**

   Remotetools für Visual Studio unterstützen nicht das Remotedebuggen auf [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Zum Debuggen einer app, wenn er ausgeführt wird, auf [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], können Sie einen Debugger aus einer älteren Version von Visual Studio lokal oder Remote Debuggen. Dies ähnelt dem Debuggen einer Anwendung unter Windows Vista, das ein Laufzeitziel des Plattformtoolsets, aber kein Remotedebuggingziel ist.

- **Statische Analyse**

   Die Windows XP-Plattformtoolsets unterstützen keine statischen Analysen, da die SAL-Anmerkungen für das [!INCLUDE[win7](../build/includes/win7_md.md)]-SDK und die Laufzeitbibliotheken nicht kompatibel sind. Wenn Sie statische Analysen für eine App durchführen möchten, die [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] unterstützt, können sie vorübergehend die Projektmappe so umschalten, dass sie zum Durchführen der Analyse das Standard-Plattformtoolset als Ziel verwendet, und dann zum Windows XP-Plattformtoolset zurückwechseln, um die App zu erstellen.

- **Debuggen von DirectX-Grafiken**

     Da der Grafikdebugger die Direct3D 9-API nicht unterstützt, kann sie nicht zum Debuggen von Apps verwendet werden, die Direct3D unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] verwenden. Wenn die App jedoch einen alternative Renderer implementiert, der die Direct3D 10- oder Direct3D 11-API verwendet, kann der Grafikdebugger verwendet werden, um Probleme mit der Verwendung dieser APIs zu diagnostizieren.

- **Erstellen von HLSL**

   Standardmäßig kompiliert das Windows XP-Toolset keine HLSL-Quellcodedateien. Zur Kompilierung von HLSL-Dateien laden Sie das June 2010 DirectX SDK herunter und installieren es und legen dann die VC-Verzeichnisse des Projekts so fest, dass es eingeschlossen ist. Weitere Informationen finden Sie unter der "DirectX-SDK registriert keine Include/Library-Pfade bei Visual Studio 2010" im Abschnitt der [June 2010 DirectX SDK-Downloadseite](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).
