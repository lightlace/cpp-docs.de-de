---
title: -ORDER (Reihenfolge von Funktionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
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
ms.openlocfilehash: 87fafb0f6eba5130524a373a065fb86ea7eacfc9
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894511"
---
# <a name="order-put-functions-in-order"></a>/ORDER (Reihenfolge von Funktionen festlegen)

Geben Sie die Verknüpfungsreihenfolge für separat Paketfunktionen (COMDAT).

## <a name="syntax"></a>Syntax

> **/ ORDER:\@**<em>Dateiname</em>

### <a name="parameters"></a>Parameter

*filename*  
Eine Textdatei, die angibt, die Verknüpfungsreihenfolge für COMDAT-Funktionen.

## <a name="remarks"></a>Hinweise

Die **/ORDER** Compileroption können Sie zum Optimieren Ihres Programms auslagerungsverhalten durch Gruppieren von einer Funktion zusammen mit den Funktionen aufgerufen. Sie können auch häufig aufgerufene Funktionen gruppieren. Diese Verfahren, bekannt als *Auslagerungsdatei optimieren* oder *Paging Optimierung*, erhöhen die Wahrscheinlichkeit, die eine aufgerufene Funktion im Arbeitsspeicher ist, wenn es erforderlich ist, und muss nicht vom Datenträger ausgelagert werden.

Wenn Sie Ihren Quellcode in einer Objektdatei kompilieren, Sie können den Compiler anweisen, platzieren jede Funktion in einen eigenen Abschnitt an, dem Namen einer *COMDAT*, mit der [/Gy (Funktionslevel-linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) Compiler -Option. Die **/ORDER** Linkeroption weist den Linker COMDATs in das ausführbare Image in der Reihenfolge positioniert Sie angeben.

Um die COMDAT-Reihenfolge anzugeben, erstellen eine *Antwortdatei*, eine Textdatei, die jede COMDAT auflistet, anhand des Namens, eines pro Zeile, in der Reihenfolge diese durch den Linker platziert werden sollen. Übergeben Sie den Namen der Datei als die *Filename* Parameter, der die **/ORDER** Option. Bei C++-Funktionen ist der Name der COMDAT den ergänzten Namen der Funktion. Verwenden Sie den nicht ergänzten Namen für die C-Funktionen, `main`, und geben Sie für C++-Funktionen als deklariert `extern "C"`. Funktionsnamen und ergänzte Namen werden Groß-/Kleinschreibung beachtet. Weitere Informationen zu ergänzten Namen, finden Sie unter [ergänzte Namen](../../build/reference/decorated-names.md).

Um Ihre COMDATs die ergänzten Namen zu suchen, verwenden die [DUMPBIN](../../build/reference/dumpbin-reference.md) des Tools [& gt; SYMBOLE](../../build/reference/symbols.md) Option in der Objektdatei. Der Linker automatisch voran, einen Unterstrich (**\_**)-Funktion, wenn der Name, mit einem Fragezeichen beginnt in der Antwort Dateinamen (**?**) oder bei der Registrierung ( **\@**). Wenn eine Quelldatei enthält example.cpp, z. B. Funktionen `int cpp_func(int)`, `extern "C" int c_func(int)` und `int main(void)`, den Befehl `DUMPBIN /SYMBOLS example.obj` diese ergänzten Namen aufgeführt:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

In diesem Fall geben die Namen als `?cpp_func@@YAHH@Z`, `c_func`, und `main` in Ihrer Antwortdatei.

Wenn mehr als ein **/ORDER** Option wird angezeigt, in den Optionen des Linkers, der letzte Suchvorgang angegeben wird wirksam.

Die **/ORDER** Option deaktiviert die inkrementelle Verknüpfung. Möglicherweise angezeigt, zu unterdrückenden linkerwarnungen [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) Wenn Sie diese Option angeben, wenn inkrementelles Verknüpfen aktiviert ist, oder wenn Sie angegeben haben die ["/ Zi" (inkrementelle PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) -Compileroption. Um diese Warnung unterdrücken möchten, können Sie die [/INCREMENTAL: No](../../build/reference/incremental-link-incrementally.md) Linkeroption, um die inkrementelle Verknüpfung deaktivieren, und Verwenden der ["/ Zi" (Generieren von PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) -Compileroption verwenden, um eine PDB-Datei ohne die inkrementelle Verknüpfung zu generieren.

> [!NOTE]
> LINK kann nicht statische Funktionen sortieren, da statische Funktionsnamen nicht öffentlichen Symbolnamen sind. Wenn **/ORDER** angegeben wird, zu unterdrückenden linkerwarnungen [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) generiert für jedes Symbol in der Order-Antwortdatei, die entweder statisch oder nicht gefunden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. Ändern der **Funktionsanordnung** Eigenschaft den Namen Ihrer Antwortdatei enthält.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)