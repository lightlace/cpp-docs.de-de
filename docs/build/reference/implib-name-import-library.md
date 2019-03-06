---
title: /IMPLIB (Name der Importbibliothek)
ms.date: 11/04/2016
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
ms.openlocfilehash: 8d3793b11e7bd0430c94d89f9d40ec3627c4eb20
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413354"
---
# <a name="implib-name-import-library"></a>/IMPLIB (Name der Importbibliothek)

> / IMPLIB:*Dateiname*

## <a name="parameters"></a>Parameter

*filename*<br/>
Ein benutzerdefinierter Name für die Bibliothek importieren. Sie können den Standardnamen ersetzt.

## <a name="remarks"></a>Hinweise

Die/IMPLIB-Option überschreibt den Standardnamen für die Importbibliothek, die Verknüpfung erstellt werden, wenn es sich um ein Programm erstellt, das Exporte enthält. Der Standardname wird gebildet, aus dem Basisnamen der Hauptausgabedatei und der Erweiterung. Lib. Ein Programm enthält Exporte aus, wenn eine oder mehrere der folgenden angegeben werden:

- Die [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) Schlüsselwort im Quellcode

- [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei

- Ein [/EXPORT](../../build/reference/export-exports-a-function.md) Spezifikation in einem LINK-Befehl

LINK ignoriert/IMPLIB, wenn keine Importbibliothek erstellt wird. Wenn keine Exporte angegeben sind, erstellt der LINK keine Importbibliothek. Wenn eine Exportdatei in den Build verwendet wird, wird links davon ausgegangen, dass eine Importbibliothek ist bereits vorhanden ist und einen nicht erstellt. Informationen über Importbibliotheken und Exportdateien können, finden Sie unter [LIB-Referenz](../../build/reference/lib-reference.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Importbibliothek** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
