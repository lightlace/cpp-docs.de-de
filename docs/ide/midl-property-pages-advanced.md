---
title: 'Eigenschaftenseiten "MIDL": Erweiterte | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6e7dde047c3311c6fd694a91c7a63fcfbcc95d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="midl-property-pages-advanced"></a>Eigenschaftenseiten "MIDL": "Erweitert"
Die **erweitert** Eigenschaftenseite in der **"MIDL"** Ordner angibt, die folgenden Compileroptionen in "MIDL":  
  
-   Aktivieren Sie die Überprüfung von Fehlern ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen von Zuordnungen ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen Sie die Grenzen ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfung der Enum-Bereich ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Verweiszeiger überprüfen ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen Sie die Daten der Stub ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Überprüfen Sie die Parameter ([/ stabile](http://msdn.microsoft.com/library/windows/desktop/aa367363)) *  
  
-   Strukturmembers ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Ausgabe ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   Vorverarbeiten C#-Optionen ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Präprozessordefinitionen ([/u](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \*/ robust ist nur für die Verwendung beim Erstellen für Windows 2000 oder höher zur Verfügung. Wenn Sie eine ATL-Projekt erstellen und, verwenden Sie möchten / stabile, ändern Sie diese Zeile in der Datei dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Informationen zum Zugreifen auf die **erweitert** Eigenschaftenseite in der **"MIDL"** Ordner finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
 Informationen zum programmgesteuert MIDL-Optionen für C++-Projekte zugreifen, finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md)