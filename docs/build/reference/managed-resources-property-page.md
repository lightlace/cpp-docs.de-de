---
title: Verwaltete Ressourcen (Eigenschaftenseite)
ms.date: 08/28/2019
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 14802996e63392bfb5fcc22096ef5f3d9db197c2
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177526"
---
# <a name="managed-resources-property-page"></a>Verwaltete Ressourcen (Eigenschaftenseite)

Die Eigenschaften Seite **verwaltete Ressourcen** macht die folgenden Eigenschaften für den verwalteten Ressourcen Compiler [Resgen. exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) verfügbar, wenn .net- C++Ressourcen in/CLI-Programmen verwendet werden:

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
