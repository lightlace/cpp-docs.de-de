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
ms.openlocfilehash: ed9d6ba12e65eac325008cb2a448abdab087ee46
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197959"
---
# <a name="midl-property-pages-advanced"></a>Eigenschaftenseiten "MIDL": "Erweitert"
Die Eigenschaftenseite **Erweitert** im Ordner **MIDL** gibt die folgenden MIDL-Compileroptionen an:  
  
-   Aktivieren der Fehlerüberprüfung ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Speicherbelegungen ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Begrenzungen ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen des Enumerationsbereichs ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Verweiszeiger ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen der Stub-Daten ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen von Parametern ([/robust](https://msdn.microsoft.com/library/windows/desktop/aa367363)) \*  
  
-   Ausrichten der Strukturmembers ([/Zp](https://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Umleiten der Ausgabe ([/o](https://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C-Präprozessoroptionen ([/cpp_opt](https://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Aufheben der Präprozessordefinitionen ([/U](https://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
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