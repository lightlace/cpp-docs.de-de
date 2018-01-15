---
title: "Konfigurieren von Programmen für Windows XP | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff80109c1f3a5e03ecb85406cdaea24804f96783
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Konfigurieren von Programmen für Windows XP
Da Visual Studio mehrere Plattformtoolsets unterstützt, können Sie abzielen, Betriebssysteme und Laufzeitbibliotheken, die die vom Standardtoolset nicht unterstützt werden. Beispielsweise durch den Wechsel des Plattformtoolsets, können C ++ 11 und C ++ 14 C ++ 17-spracherweiterungen unterstützt, die vom Visual C++-Compiler in Visual Studio zum Erstellen von apps, die auf [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Sie können auch ältere Plattformtoolsets verwenden, um binärkompatiblen Legacycode zu verwalten und dennoch die neuesten Funktionen von Visual Studio-IDE nutzen.  
  
> [!NOTE]
>  Bei Verwendung von [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)], müssen Sie installieren [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] Update 4 hinzuzufügende Plattformtoolset-Unterstützung für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Zum Herunterladen und installieren eine Kopie des [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] Update 4, finden Sie unter [Microsoft Visual Studio Express 2012 für Windows Desktop](http://go.microsoft.com/fwlink/p/?linkid=265464) im Microsoft Download Center. Installieren Sie dann [Visual Studio 2012 Update 4](http://go.microsoft.com/fwlink/p/?linkid=335900) , die das v110_xp-Plattformtoolset zu erhalten. Verwenden Sie Windows Update, um nach der Installation die aktuellsten Softwareupdates abzurufen.  
  
## <a name="windows-xp-targeting-experience"></a>Windows XP als Ziel  
 Die Windows XP-Plattformtoolset, die in Visual Studio enthalten ist, ist eine Version von der [!INCLUDE[win7](../build/includes/win7_md.md)] SDK, das im Lieferumfang [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], jedoch den aktuellen C++-Compiler verwendet. Es konfiguriert außerdem Projekteigenschaften auf entsprechende Standardwerte, z. B. die Spezifikation eines kompatiblen Linkers kompatibel für die Zielfestlegung auf Elementebene. Nur Windows desktop-apps, die erstellt werden, mithilfe der Windows XP-Plattformtoolset weiterlaufen [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], aber diese apps können auch auf neueren Windows-Betriebssysteme ausführen.  
  
#### <a name="to-target-windows-xp"></a>So entwickeln Sie für Windows XP  
  
1.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  In der **Eigenschaftenseiten** Dialogfeld für das Projekt unter **Konfigurationseigenschaften**, **allgemeine**legen die **Plattformtoolset** die Eigenschaft auf das gewünschte Windows XP-Toolset. Wählen Sie z. B. **Visual Studio 2015 – Windows XP (v140_xp)** zum Erstellen von Code für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] mithilfe des Microsoft Visual C++ 2015-Compilers.  
  
### <a name="c-runtime-support"></a>C++-Laufzeitunterstützung  
 Zusammen mit dem Windows XP-Plattformtoolset, die C-Laufzeitbibliothek (CRT), C++-Standardbibliothek, Active Template Library (ATL), Concurrency Runtime-Bibliothek (ConCRT), Parallel Patterns Library (PPL), Microsoft Foundation Class-Bibliothek (MFC) und C++ AMP (C++- Accelerated Massive Programmierung) Bibliothek enthalten Laufzeitunterstützung für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Für diese Betriebssysteme, die minimalen unterstützten Versionen sind [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 (SP3) für X86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 (SP2) für X64, und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 (SP2) für x X86 und X64.  
  
 Diese Bibliotheken werden durch die von Visual Studio installiert ist, abhängig von der Ziel-Plattformtoolsets unterstützt:  
  
|Bibliothek|Standard-Plattformtoolset mit Windows-Desktop-Apps als Ziel|Standard-Plattformtoolset mit [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-Apps als Ziel|Windows XP-Plattformtoolset mit [!INCLUDE[winxp](../build/includes/winxp_md.md)],[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] als Ziel|  
|-------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|C++-Standardbibliothek|X|X|X|  
|ATL|X|X|X|  
|ConCRT/PPL|X|X|X|  
|MFC|X||X|  
|C++ AMP|X|X||  
  
> [!NOTE]
>  Apps, die in C++/CLI geschrieben sind und .NET Framework 4 als Ziel haben, können unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] ausgeführt werden.  
  
### <a name="differences-between-the-toolsets"></a>Unterschiede zwischen den Toolsets  
 Aufgrund von Unterschieden bei Plattform-und bibliotheksunterstützung ist ist die Entwicklungsumgebung für apps, die ein Windows XP-Plattformtoolset verwenden, nicht so umfassend wie für apps, die die Standard-Plattformtoolset Visual Studio verwenden.  
  
-   **C++-Sprachfunktionen**  
  
     Nur C++-Sprachfeatures in implementiert [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] werden in apps, die das v110_xp-Plattformtoolset verwenden unterstützt. Nur C++-Sprachfeatures in implementiert [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] werden in apps, die das v120_xp-Plattformtoolset verwenden unterstützt. Visual Studio verwendet den entsprechenden Compiler bei der Erstellung der älteren Plattformtoolsets. Verwenden Sie das neueste Windows XP-Plattformtoolset, um zusätzliche Funktionen der Programmiersprache C++ in dieser Version des Compilers implementiert nutzen.  
  
-   **Remotedebuggen**  
  
     Remotetools für Visual Studio unterstützen nicht das Remotedebuggen auf [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Zum Debuggen einer app, wenn er ausgeführt wird, auf [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], können Sie einen Debugger aus einer älteren Version von Visual Studio lokal oder Remote Debuggen. Dies ähnelt dem Debuggen einer Anwendung unter Windows Vista, das ein Laufzeitziel des Plattformtoolsets, aber kein Remotedebuggingziel ist.  
  
-   **Statische Analyse**  
  
     Die Windows XP-Plattformtoolsets unterstützen keine statischen Analysen, da die SAL-Anmerkungen für das [!INCLUDE[win7](../build/includes/win7_md.md)]-SDK und die Laufzeitbibliotheken nicht kompatibel sind. Wenn Sie statische Analysen für eine App durchführen möchten, die [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] unterstützt, können sie vorübergehend die Projektmappe so umschalten, dass sie zum Durchführen der Analyse das Standard-Plattformtoolset als Ziel verwendet, und dann zum Windows XP-Plattformtoolset zurückwechseln, um die App zu erstellen.  
  
-   **Debuggen von DirectX-Grafiken**  
  
     Da der Grafikdebugger die Direct3D 9-API nicht unterstützt, kann sie nicht zum Debuggen von Apps verwendet werden, die Direct3D unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] verwenden. Wenn die App jedoch einen alternative Renderer implementiert, der die Direct3D 10- oder Direct3D 11-API verwendet, kann der Grafikdebugger verwendet werden, um Probleme mit der Verwendung dieser APIs zu diagnostizieren.  
  
-   **Erstellen von HLSL**  
  
     Standardmäßig kompiliert das Windows XP-Toolset keine HLSL-Quellcodedateien. Zur Kompilierung von HLSL-Dateien laden Sie das June 2010 DirectX SDK herunter und installieren es und legen dann die VC-Verzeichnisse des Projekts so fest, dass es eingeschlossen ist. Weitere Informationen finden Sie unter der "DirectX-SDK registriert keine Include/Library-Pfade bei Visual Studio 2010" im Abschnitt der [June 2010 DirectX SDK-Downloadseite](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).