---
title: "Konfigurieren von C++ 11-Programmen f&#252;r Windows XP"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: 14
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Konfigurieren von C++ 11-Programmen f&#252;r Windows XP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Da [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] mehrere Plattformtoolsets unterstützt, können Sie Betriebssysteme und Laufzeitbibliotheken als Ziel festlegen, die vom Standardtoolset nicht unterstützt werden.  Beispielsweise können Sie die C\+\+11\-Spracherweiterungen, \-Compiler, \-Bibliotheken und andere Features verwenden, die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] implementiert sind, um Apps für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] zu erstellen.  Sie können ältere Plattformtoolsets verwenden, um binärkompatiblen Legacycode zu verwalten und dennoch die neuesten Features der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-IDE zu nutzen.  
  
> [!NOTE]
>  Sie müssen [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] Update 4 installieren, um Plattformtoolset\-Unterstützung für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] zu [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] hinzuzufügen.  Informationen zum Herunterladen und Installieren einer Kopie von [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] Update 4 finden Sie unter [Microsoft Visual Studio Express 2012 für Windows Desktop](http://go.microsoft.com/fwlink/?LinkID=265464) im Microsoft Download Center.  Installieren Sie dann [Visual Studio 2012 Update 4](http://go.microsoft.com/fwlink/?LinkID=335900), um das v110\_xp\-Plattformtoolset zu erhalten.  Verwenden Sie Windows Update, um nach der Installation die aktuellsten Softwareupdates abzurufen.  
  
## Windows XP als Ziel  
 Das in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthaltene Windows XP\-Plattformtoolset ist eine Version des [!INCLUDE[win7](../build/includes/win7_md.md)]\-SDK, das in [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)] enthalten war, verwendet jedoch den aktuellen C\+\+\-Compiler.  Es konfiguriert außerdem Projekteigenschaften auf entsprechende Standardwerte, z. B. die Spezifikation eines kompatiblen Linkers kompatibel für die Zielfestlegung auf Elementebene.  Nur Windows Desktop\-Apps, die unter Verwendung des Windows XP\-Plattformtoolsets erstellt werden, können unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] ausgeführt werden; diese Apps können jedoch auch unter neueren Betriebssysteme ausgeführt werden, z. B. Windows Vista, [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/includes/winsvr08_md.md)], [!INCLUDE[win8](../build/includes/win8_md.md)] oder [!INCLUDE[winserver8](../build/includes/winserver8_md.md)].  
  
#### So entwickeln Sie für Windows XP  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Legen Sie im Dialogfeld **Eigenschaftenseiten** für das Projekt unter **Konfigurationseigenschaften**, **Allgemein** die Eigenschaft **Platform Toolset** auf das gewünschte Windows XP\-Toolset fest.  Wählen Sie z. B. **Visual Studio 2012 – Windows XP \(v110\_xp\)** aus, um Code zu erstellen, der mit Microsoft Visual C\+\+ 2012 Redistributable\-Bibliotheken binärkompatibel ist.  
  
### C\+\+\-Laufzeitunterstützung  
 Die C\-Laufzeitbibliothek \(CRT\), Standard Template Library \(STL\), Active Template Library \(ATL\), Concurrency Runtime\-Bibliothek \(ConCRT\), Parallel Patterns Library \(PPL\), Microsoft Foundation Class\-Bibliothek \(MFC\) und C\+\+ AMP \(C\+\+ Accelerated Massive Programming\)\-Bibliothek enthalten neben dem Windows XP\-Plattformtoolset Laufzeitunterstützung für [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Für diese Betriebssysteme werden folgenden Versionen unterstützt: [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 \(SP3\) für x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 \(SP2\) für x64 und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 \(SP2\) für x86 und x64.  
  
 Diese Bibliotheken werden in Abhängigkeit vom Ziel von den von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installierten Plattformtoolsets unterstützt:  
  
|Bibliothek|Standard\-Plattformtoolset mit Windows\-Desktop\-Apps als Ziel|Standard\-Plattformtoolset mit [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps als Ziel|Windows XP\-Plattformtoolset mit [!INCLUDE[winxp](../build/includes/winxp_md.md)],[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] als Ziel|  
|----------------|--------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|STL|X|X|X|  
|ATL|X|X|X|  
|ConCRT\/PPL|X|X|X|  
|MFC|X||X|  
|C\+\+ AMP|X|X||  
  
> [!NOTE]
>  Apps, die in C\+\+\/CLI geschrieben sind und .NET Framework 4 als Ziel haben, können unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] ausgeführt werden.  
  
### Unterschiede zwischen den Toolsets  
 Aufgrund von Unterschieden bei Plattform\- und Bibliotheksunterstützung ist die Entwicklungsumgebung für Apps, die ein Windows XP\-Plattformtoolset verwenden, nicht so umfassend wie für Apps, die das standardmäßige [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Plattformtoolset verwenden.  
  
-   **Features der Programmiersprache C\+\+**  
  
     In Apps, die das v110\_xp\-Plattformtoolset verwenden, werden nur die Features der Programiersprache C\+\+11 unterstützt, die in [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] implementiert sind.  In Apps, die das v120\_xp\-Plattformtoolset verwenden, werden nur die Features der Programiersprache C\+\+11 unterstützt, die in [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] implementiert sind.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] verwendet den entsprechenden Compiler bei der Erstellung der älteren Plattformtoolsets.  Verwenden Sie ein neueres Windows XP\-Plattformtoolset. um weitere C\+\+11\-Features zu nutzen, die in dieser Version implementiert sind.  
  
-   **Remotedebuggen**  
  
     Remotetools für [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] unterstützen das Remotedebuggen unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] nicht.  Zum Debuggen einer App, die unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] ausgeführt wird, können Sie einen Debugger aus einer älteren Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] verwenden, um diese lokal oder remote zu debuggen.  Dies ähnelt dem Debuggen einer Anwendung unter Windows Vista, das ein Laufzeitziel des Plattformtoolsets, aber kein Remotedebuggingziel ist.  
  
-   **Statische Analyse**  
  
     Die Windows XP\-Plattformtoolsets unterstützen keine statischen Analysen, da die SAL\-Anmerkungen für das [!INCLUDE[win7](../build/includes/win7_md.md)]\-SDK und die Laufzeitbibliotheken nicht kompatibel sind.  Wenn Sie statische Analysen für eine App durchführen möchten, die [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] unterstützt, können sie vorübergehend die Projektmappe so umschalten, dass sie zum Durchführen der Analyse das Standard\-Plattformtoolset als Ziel verwendet, und dann zum Windows XP\-Plattformtoolset zurückwechseln, um die App zu erstellen.  
  
-   **Debuggen von DirectX\-Grafiken**  
  
     Da der Grafikdebugger die Direct3D 9\-API nicht unterstützt, kann sie nicht zum Debuggen von Apps verwendet werden, die Direct3D unter [!INCLUDE[winxp](../build/includes/winxp_md.md)] oder [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] verwenden.  Wenn die App jedoch einen alternative Renderer implementiert, der die Direct3D 10\- oder Direct3D 11\-API verwendet, kann der Grafikdebugger verwendet werden, um Probleme mit der Verwendung dieser APIs zu diagnostizieren.  
  
-   **Erstellen von HLSL**  
  
     Standardmäßig kompiliert das Windows XP\-Toolset keine HLSL\-Quellcodedateien.  Zur Kompilierung von HLSL\-Dateien laden Sie das June 2010 DirectX SDK herunter und installieren es und legen dann die VC\-Verzeichnisse des Projekts so fest, dass es eingeschlossen ist.  Weitere Informationen finden Sie im Abschnitt „DirectX\-SDK registriert keine Include\/Library\-Pfade bei Visual Studio 2010“ der [June 2010 DirectX SDK\-Downloadseite](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).