---
title: Verwaltet Ressourcen Eigenschaftenseite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
dev_langs:
- C++
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2922a0a92a121d6838478daaf2c32f1c7a630d21
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="managed-resources-property-page"></a>Verwaltete Ressourcen (Eigenschaftenseite)
Aktiviert die Einstellungen für den Ressourcencompiler.  
  
 Die **verwaltete Ressourcen** Eigenschaftenseite enthält die folgenden Eigenschaften:  
  
 **Logische Name der Ressource**  
 Gibt an, die *logischen Namen* der generierten temporären RESOURCES-Datei. Der logische Name ist der Name verwendet, um die Ressource zu laden. Wenn kein logischer Name angegeben ist, wird der Dateiname der Ressourcendatei (.resx) als der logische Name verwendet.  
  
 **Name der Ausgabedatei**  
 Gibt den Namen der endgültigen Ausgabedatei, der die Ressourcendatei (.resx) zur beiträgt.  
  
 **Lokalisierte Ressourcen**  
 Gibt an, ob die angegebene RESX-Datei, die Standardressourcen oder einer Satelliten-DLL beiträgt.  
  
 Informationen zum Zugreifen auf die **verwaltete Ressourcen** auf der Seite finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Unter Verwendung von RC (RC Command-Line)](http://msdn.microsoft.com/library/windows/desktop/aa381055)   
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)   
 [/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)](../build/reference/assemblyresource-embed-a-managed-resource.md)