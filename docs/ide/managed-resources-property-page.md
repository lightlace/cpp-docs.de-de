---
title: Verwaltete Ressourcen (Eigenschaftenseite)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 7445c9634ddd242935f3304efae76cc9eb8f007f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655610"
---
# <a name="managed-resources-property-page"></a>Verwaltete Ressourcen (Eigenschaftenseite)

Aktiviert Einstellungen für den Ressourcencompiler.

Die Eigenschaftenseite **Verwaltete Ressourcen** enthält die folgenden Eigenschaften:

- **Logischer Ressourcenname**

   Gibt den *logischen Namen* der generierten RESOURCES-Zwischendatei an. Der logische Name ist der Name, der zum Laden der Ressource verwendet wird. Wenn kein logischer Name angegeben wird, wird der Dateiname der Ressourcendatei (RESX) als logischer Name verwendet.

- **Name der Ausgabedatei**

   Gibt den Namen der endgültigen Ausgabedatei an, zu der diese Ressourcendatei (RESX) beiträgt.

- **Standardmäßig lokalisierte Ressourcen**

   Gibt an, ob die angegebene RESX-Datei zu den Standardressourcen oder einer Satelliten-DLL beiträgt.

Informationen zum Zugreifen auf die Eigenschaftenseiten **Verwaltete Ressourcen** finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[Verwenden des Ressourcencompilers (RC-Befehlszeile)](/windows/desktop/menurc/using-rc-the-rc-command-line-)<br>
[Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)<br>
[/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)](../build/reference/assemblyresource-embed-a-managed-resource.md)