---
title: "Eigenschaftenseiten &quot;MIDL&quot;: &quot;Erweitert&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCMidlTool.ErrorCheckBounds"
  - "VC.Project.VCMidlTool.ErrorCheckStubData"
  - "VC.Project.VCMidlTool.ErrorCheckAllocations"
  - "VC.Project.VCMidlTool.CPreprocessOptions"
  - "VC.Project.VCMidlTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCMidlTool.EnableErrorChecks"
  - "VC.Project.VCMidlTool.RedirectOutputAndErrors"
  - "VC.Project.VCMidlTool.ErrorCheckEnumRange"
  - "VC.Project.VCMidlTool.StructMemberAlignment"
  - "VC.Project.VCMidlTool.ErrorCheckRefPointers"
  - "VC.Project.VCMidlTool.ValidateParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eigenschaftenseiten „MIDL“"
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenseiten &quot;MIDL&quot;: &quot;Erweitert&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Auf der Eigenschaftenseite **Erweitert** des Ordners **MIDL** werden folgende MIDL\-Compileroptionen festgelegt:  
  
-   Fehlerüberprüfung aktivieren \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Zuordnungen überprüfen \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Begrenzungen überprüfen \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Enumerationsbereich \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Verweiszeiger überprüfen \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Stubdaten überprüfen \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Parameter überprüfen \([\/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)\) \*  
  
-   Ausrichten des Strukturmembers \([\/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388)\)  
  
-   Ausgabe umleiten \([\/o](http://msdn.microsoft.com/library/windows/desktop/aa367351)\)  
  
-   C\-Präprozessoroptionen \([\/cpp\_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318)\)  
  
-   Präprozessordefinitionen aufheben \([\/U](http://msdn.microsoft.com/library/windows/desktop/aa367373)\)  
  
 **\* \/robust** kann nur verwendet werden, wenn ein Build für einen Computer mit Windows 2000 oder einem späteren Betriebssystem erstellt wird.  Wenn Sie ein ATL\-Projekt erstellen und **\/robust** verwenden möchten, ändern Sie diese Zeile in der Datei **dlldatax.c**:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Informationen dazu, wie Sie auf die Eigenschaftenseite **Erweitert** im Ordner **MIDL** zugreifen, finden Sie unter [Gewusst wie: Festlegen von Projekteigenschaften mit Eigenschaftenseiten](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
 Informationen über den programmgesteuerten Zugriff auf MIDL\-Optionen für C\+\+\-Projekte finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## Siehe auch  
 [Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md)