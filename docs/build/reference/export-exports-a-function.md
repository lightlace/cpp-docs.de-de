---
title: / EXPORT (exportiert eine Funktion) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16ec6be15635ebfc085615015b1221231645970d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894793"
---
# <a name="export-exports-a-function"></a>/EXPORT (Funktion exportieren)

Exportiert eine Funktion nach Name oder Ordinalzahl oder Daten von Ihrem Programm an.

## <a name="syntax"></a>Syntax

> **/ EXPORT:**<em>Eintragsname</em>[**,\@**<em>ordinal</em>[**, NONAME**]] [**, Daten**]

## <a name="remarks"></a>Hinweise

Mit der Option/Export können Sie eine Funktion von Ihrem Programm exportieren, sodass andere Programme, die Funktion aufrufen können. Sie können auch Daten exportieren. Exporte werden in der Regel in eine DLL-Datei definiert.

Die *Eintragsname* ist der Name der Funktion oder des Elements, wie die vom aufrufenden Programm verwendet werden. `ordinal` Gibt einen Index in die Exporttabelle im Bereich von 1 bis 65.535. Wenn Sie keinen angeben `ordinal`, LINK weist ein. Die **NONAME** Schlüsselwort exportiert die Funktion nur als Ordnungszahl, ohne eine *Eintragsname*.

Die **Daten** -Schlüsselwort Gibt an, dass das exportierte Element ein Datenelement ist. Das Datenelement in das Clientprogramm muss deklariert werden, mithilfe von **"extern" von "__declspec(dllimport)" "**.

Es gibt drei Methoden zum Exportieren einer Definition, aufgelistet in empfohlener Reihenfolge von Nutzen:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) im Quellcode

2. Ein [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei

3. Eine/Export-Spezifikation in einem Linkbefehl

Alle drei Methoden können im selben Programm verwendet werden. Wenn der LINK ein Programm erstellt, das Exporte enthält, wird auch eine Importbibliothek, es sei denn, eine .exp-Datei in den Build verwendet wird.

LINK-verwendet die ergänzten Formen von Bezeichnern. Der Compiler ergänzt einen Bezeichner, wenn es sich um die OBJ-Datei erstellt. Wenn *Eintragsname* wird angegeben, um dem Linker in seiner nicht ergänzten form (im Quellcode angezeigt), LINK versucht, mit dem Namen übereinstimmen. Wenn sie eine eindeutige Übereinstimmung finden kann, wird links eine Fehlermeldung ausgegeben. Verwenden der [DUMPBIN](../../build/reference/dumpbin-reference.md) Tool zum Abrufen der [ergänzten Namen](../../build/reference/decorated-names.md) Form eines Bezeichners, wenn Sie es dem Linker angeben möchten.

> [!NOTE]
> Geben Sie die ergänzte Form des C-Bezeichner, die deklariert werden keine `__cdecl` oder `__stdcall`.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

2. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

3. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
[Linkeroptionen](../../build/reference/linker-options.md)