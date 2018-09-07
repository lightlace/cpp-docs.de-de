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
ms.openlocfilehash: 5063eae507ee6c83cbed2ae7fc92679098b91f36
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104618"
---
# <a name="export-exports-a-function"></a>/EXPORT (Funktion exportieren)

Exportiert eine Funktion nach Name oder Ordinalzahl oder Daten von Ihrem Programm an.

## <a name="syntax"></a>Syntax

> **/ EXPORT:**<em>Eintragsname</em>[**,\@**<em>ordinal</em>[**, NONAME**]] [**, Daten**]

## <a name="remarks"></a>Hinweise

Die **/EXPORT** Option gibt an, eine Funktion oder ein Datenelement aus Ihrem Programm zu exportieren, sodass andere Programme rufen Sie die Funktion oder verwenden Sie die Daten können. Exporte werden in der Regel in eine DLL-Datei definiert.

Die *Eintragsname* ist der Name der Funktion oder des Elements, wie die vom aufrufenden Programm verwendet werden. *Ordinal* gibt Sie einen Index in der Exporttabelle im Bereich von 1 bis 65.535 sein, wenn Sie keinen angeben *ordinal*, LINK weist ein. Die **NONAME** Schlüsselwort exportiert die Funktion nur als Ordnungszahl, ohne eine *Eintragsname*.

Die **Daten** -Schlüsselwort Gibt an, dass das exportierte Element ein Datenelement ist. Das Datenelement in das Clientprogramm muss deklariert werden, mithilfe von **"extern" von "__declspec(dllimport)" "**.

Es gibt vier Möglichkeiten für das Exportieren einer Definition, aufgelistet in empfohlener Reihenfolge von Nutzen:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) im Quellcode

1. Ein [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei

1. Eine/Export-Spezifikation in einem Linkbefehl

1. Ein [Kommentar](../../preprocessor/comment-c-cpp.md) -Anweisung im Quellcode, der das Formular `#pragma comment(linker, "/export: definition ")`.

Alle diese Methoden können im selben Programm verwendet werden. Wenn der LINK ein Programm erstellt, das Exporte enthält, wird auch eine Importbibliothek, es sei denn, eine .exp-Datei in den Build verwendet wird.

LINK-verwendet die ergänzten Formen von Bezeichnern. Der Compiler ergänzt einen Bezeichner, wenn es sich um die OBJ-Datei erstellt. Wenn *Eintragsname* wird angegeben, um dem Linker in seiner nicht ergänzten form (im Quellcode angezeigt), LINK versucht, mit dem Namen übereinstimmen. Wenn sie eine eindeutige Übereinstimmung finden kann, wird links eine Fehlermeldung ausgegeben. Verwenden der [DUMPBIN](../../build/reference/dumpbin-reference.md) Tool zum Abrufen der [ergänzten Namen](../../build/reference/decorated-names.md) Form eines Bezeichners, wenn Sie es dem Linker angeben möchten.

> [!NOTE]
> Geben Sie die ergänzte Form des C-Bezeichner, die deklariert werden keine `__cdecl` oder `__stdcall`.

Wenn Sie müssen einen nicht ergänzten Funktionsnamen exportieren und anderen Exporte abhängig von der Buildkonfiguration (z. B. in 32-Bit oder 64-Bit-Builds) haben, können Sie verschiedene DEF-Dateien für jede Konfiguration. (Bedingte präprozessoranweisungen sind in der DEF-Dateien nicht zulässig.) Als Alternative können Sie eine `#pragma comment` Anweisung vor der Deklaration einer Funktion wie der hier gezeigten `PlainFuncName` ist von der nicht ergänzte Namen, und `_PlainFuncName@4` ist der ergänzte Name der Funktion:

```cpp
#pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
BOOL CALLBACK PlainFuncName( Things * lpParams)
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

2. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

3. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
[Linkeroptionen](../../build/reference/linker-options.md)
