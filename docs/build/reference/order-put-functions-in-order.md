---
title: -Reihenfolge (Reihenfolge von Funktionen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
dev_langs:
- C++
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de9b0fb629a1bf984929ec170f05e25e740e9cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="order-put-functions-in-order"></a>/ORDER (Reihenfolge von Funktionen festlegen)

Geben Sie die Verknüpfungsreihenfolge für separat Paketfunktionen (COMDAT).

## <a name="syntax"></a>Syntax

>/ ORDER: @*Dateiname*

### <a name="parameters"></a>Parameter

*filename*  
Eine Textdatei, die die Verknüpfungsreihenfolge COMDAT-Funktionen angibt.

## <a name="remarks"></a>Hinweise

Die **/ORDER** (Compileroption) können Sie zur Optimierung des Programms einheitlicheres Paginierungsverhalten durch Gruppieren von einer Funktion zusammen mit den Funktionen aufruft. Sie können auch häufig aufgerufene Funktionen gruppieren. Diese Verfahren, bezeichnet als *Auslagerungsdatei optimieren* oder *Paging Optimierung*, erhöht sich die Wahrscheinlichkeit, die eine aufgerufene Funktion im Arbeitsspeicher ist, wenn es erforderlich ist und nicht vom Datenträger ausgelagert werden müssen.

Beim Kompilieren von Quellcode in einer Objektdatei, Sie können den Compiler anweisen, jede Funktion in einem eigenen Abschnitt namens zu versetzen einer *COMDAT*, mithilfe der [/Gy (Funktionslevel-linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) Compiler -Option. Die **/ORDER** (Linkeroption) weist den Linker an COMDATs in das ausführbare Image in der Reihenfolge platzieren Sie angeben.

Um die COMDAT-Reihenfolge anzugeben, erstellen eine *Antwortdatei*, eine Textdatei, die jede COMDAT auflistet, anhand des Namens, eines pro Zeile, in der Reihenfolge, die Sie vom Linker platziert werden sollen. Übergeben Sie den Namen der Datei als die *Filename* Parameter von der **/ORDER** Option. Bei C++-Funktionen ist der Name einer COMDAT den ergänzten Namen der Funktion. Verwenden Sie den nicht ergänzten Namen für die C-Funktionen `main`, und Sie für C++-Funktionen als deklariert `extern "C"`. Funktionsnamen und ergänzten Namen werden Groß-/Kleinschreibung beachtet. Weitere Informationen über ergänzte Namen finden Sie unter [ergänzte Namen](../../build/reference/decorated-names.md). 

Um Ihre COMDATs die ergänzten Namen zu ermitteln, verwenden die [DUMPBIN](../../build/reference/dumpbin-reference.md) des Tools [/SYMBOLS](../../build/reference/symbols.md) Option in der Objektdatei. Der Linker automatisch einen Unterstrich voran (\_) Funktion Namen in der Antwort Datei, es sei denn, beginnt der Name der durch ein Fragezeichen (?) oder at-Zeichen (@). Wenn eine Quelldatei enthält example.cpp, z. B. Funktionen `int cpp_func(int)`, `extern "C" int c_func(int)` und `int main(void)`, den Befehl `DUMPBIN /SYMBOLS example.obj` diese ergänzten Namen aufgeführt:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

In diesem Fall geben Sie die Namen als `?cpp_func@@YAHH@Z`, `c_func`, und `main` in der Antwortdatei.

Wenn mehr als ein **/ORDER** Option wird angezeigt, in den Optionen des Linkers, das letzte Lesezeichen, angegeben in Kraft.

Die **/ORDER** -Option wird inkrementelles Verknüpfen deaktiviert. Möglicherweise linkerwarnung [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) Wenn Sie diese Option angeben, wenn inkrementelle Verknüpfung aktiviert ist, oder wenn Sie angegeben haben die [/Zi (inkrementelle PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) -Compileroption. Um diese Warnung zu unterdrücken, verwenden Sie die [Standardlink](../../build/reference/incremental-link-incrementally.md) Linkeroption, um inkrementelle Verknüpfung deaktivieren, und verwenden Sie die [/Zi (PDB generieren)](../../build/reference/z7-zi-zi-debug-information-format.md) Compileroption, um eine PDB-Datei ohne inkrementelle Verknüpfungen zu generieren.

> [!NOTE]
> LINK kann nicht statische Funktionen sortieren, da statische Funktionsnamen nicht öffentliche Symbolnamen sind. Wenn **/ORDER** angegeben wird, zu unterdrückenden linkerwarnungen [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) generiert für jedes Symbol in der Reihenfolge Antwortdatei, die entweder statisch oder nicht gefunden wird.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  

1. Klicken Sie unter **Konfigurationseigenschaften**öffnen **Linker** und wählen Sie dann die **Optimierung** Eigenschaftenseite.

1. Ändern der **Reihenfolge Funktion** Eigenschaft, um den Namen der Antwortdatei aufzunehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)