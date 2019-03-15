---
title: /H (Länge externer Namen beschränken)
ms.date: 09/05/2018
f1_keywords:
- /h
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
ms.openlocfilehash: bdd3da8d3a5165262c00bc3475122e31f5770726
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811263"
---
# <a name="h-restrict-length-of-external-names"></a>/H (Länge externer Namen beschränken)

Veraltet. Beschränkt die Länge externer Namen.

## <a name="syntax"></a>Syntax

> **/ H**<em>Anzahl</em>

## <a name="arguments"></a>Argumente

*Anzahl*<br/>
Gibt die maximale Länge externer Namen, die in einem Programm zulässig.

## <a name="remarks"></a>Hinweise

Standardmäßig ist die Länge externer (öffentlicher) Namen 2.047 Zeichen. Dies gilt auch für C- und C++-Programme. Mithilfe von **/h** nur verringern Sie die maximale zulässige Länge von Bezeichnern, nicht erhöht werden kann. Ein Leerzeichen zwischen **/h** und *Anzahl* ist optional.

Wenn ein Programm mit Namen mit mehr als enthält *Anzahl*, die zusätzlichen Zeichen werden ignoriert. Wenn Sie ein Programm ohne Kompilieren **/h** und ein Bezeichner maximal 2.047 Zeichen enthält, generiert der Compiler [Schwerwiegender Fehler C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md).

Die maximale Länge enthält alle vom Compiler erstellten vorangestellten Unterstrich (**\_**) oder bei der Registrierung (**\@**). Diese Zeichen sind Teil des Bezeichners, und nehmen einen wichtigen Platz.

- Der Compiler Fügt einen führenden Unterstrich (**\_**) Namen geändert, indem die `__cdecl` (Standard) und `__stdcall` Aufrufen von Konventionen, mit einem führenden at-Zeichen (**\@** ), Namen, die geändert, indem die `__fastcall` Aufrufkonvention.

- Der Compiler fügt Größe Argumentinformationen an Namen geändert, indem die `__fastcall` und `__stdcall` Aufrufkonventionen und C++-Namen Typinformationen hinzugefügt.

Möglicherweise **/h** nützlich:

- Beim Erstellen von mehreren Sprachen oder portable Programme.

- Wenn Sie Tools, die auf die Länge der externe Bezeichner schränkt verwenden.

- Wenn Sie die Menge des Speicherplatzes zu beschränken, die Symbole in einem Debugbuild verwenden möchten.

Das folgende Beispiel zeigt Verwendung **/h** Fehler entstehen können, wenn zu viele Bezeichner Länge beschränkt sind:

```cpp
// compiler_option_H.cpp
// compile with: /H5
// processor: x86
// LNK2005 expected
void func1(void);
void func2(void);

int main() { func1(); }

void func1(void) {}
void func2(void) {}
```

Sie müssen auch vorsichtig mit der **/h** Option aufgrund vordefinierter. Wenn die maximale Bezeichnerlänge zu klein ist, werden bestimmte vordefinierte Bezeichner nicht aufgelöste sowie bestimmte Bibliothek Funktionsaufrufe. Z. B. wenn die `printf` Funktion wird verwendet, und die Option **/H5** angegeben wird, zum Zeitpunkt der Kompilierung auf das Symbol **_prin als** erstellt werden, um verweisen `printf`, und dies wird nicht gefunden in der Bibliothek.

Verwenden von **/h** ist nicht kompatibel mit [/GL (Whole Program Optimization)](gl-whole-program-optimization.md).

Die **/h** Option ist seit Visual Studio 2005 als veraltet markiert; die maximale Länge wurde erhöht und **/h** wird nicht mehr benötigt. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
