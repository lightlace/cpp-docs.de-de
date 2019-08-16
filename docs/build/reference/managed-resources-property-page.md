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
ms.openlocfilehash: 97cf05f881949444879b0d48e3b3c2703a614985
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498232"
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

Informationen dazu, wie Sie auf die Eigenschaften Seite für **verwaltete Ressourcen** zugreifen, finden Sie unter [festlegen C++ von Compiler-und Buildeigenschaften in Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[Verwenden des Ressourcencompilers (RC-Befehlszeile)](/windows/win32/menurc/using-rc-the-rc-command-line-)<br>
[C++Referenz zur Projekteigenschaften Seite](property-pages-visual-cpp.md)<br>
[/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)](assemblyresource-embed-a-managed-resource.md)
