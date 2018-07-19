---
title: Eigenschaftenseite „Verwaltete Ressourcen“ | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340358"
---
# <a name="managed-resources-property-page"></a>Verwaltete Ressourcen (Eigenschaftenseite)
Aktiviert Einstellungen für den Ressourcencompiler.  
  
 Die Eigenschaftenseite **Verwaltete Ressourcen** enthält die folgenden Eigenschaften:  
  
 **Logischer Ressourcenname**  
 Gibt den *logischen Namen* der generierten RESOURCES-Zwischendatei an. Der logische Name ist der Name, der zum Laden der Ressource verwendet wird. Wenn kein logischer Name angegeben wird, wird der Dateiname der Ressourcendatei (RESX) als logischer Name verwendet.  
  
 **Name der Ausgabedatei**  
 Gibt den Namen der endgültigen Ausgabedatei an, zu der diese Ressourcendatei (RESX) beiträgt.  
  
 **Standardmäßig lokalisierte Ressourcen**  
 Gibt an, ob die angegebene RESX-Datei zu den Standardressourcen oder einer Satelliten-DLL beiträgt.  
  
 Informationen zum Zugreifen auf die Eigenschaftenseiten **Verwaltete Ressourcen** finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Using RC (The RC Command Line) (Verwenden des Ressourcencompilers (die RC-Befehlszeile))](http://msdn.microsoft.com/library/windows/desktop/aa381055)   
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)   
 [/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)](../build/reference/assemblyresource-embed-a-managed-resource.md)