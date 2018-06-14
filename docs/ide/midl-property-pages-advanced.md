---
title: 'MIDL-Eigenschaftenseiten: Erweitert | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f87518c23848cea91a3e3c48361aa0a63fa88a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330803"
---
# <a name="midl-property-pages-advanced"></a>Eigenschaftenseiten "MIDL": "Erweitert"
Die Eigenschaftenseite **Erweitert** im Ordner **MIDL** gibt die folgenden MIDL-Compileroptionen an:  
  
-   Aktivieren der Fehlerüberprüfung ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Speicherbelegungen ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Begrenzungen ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen des Enumerationsbereichs ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Verweiszeiger ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Stub-Daten ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen von Parametern ([/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363))*  
  
-   Ausrichten der Strukturmembers ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Umleiten der Ausgabe ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C-Präprozessoroptionen ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Aufheben der Präprozessordefinitionen ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \*/robust wird nur bei der Erstellung für einen Computer mit Windows 2000 oder höher verwendet. Wenn Sie ein ATL-Projekt erstellen und /robust verwenden möchten, müssen Sie die folgende Zeile in der Datei „dlldatax.c“ ändern:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Informationen über das Zugreifen auf die Eigenschaftenseite **Erweitert** im Ordner **MIDL** finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).  
  
 Informationen über den programmgesteuerten Zugriff auf die MIDL-Optionen für C++-Projekte finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md)