---
title: /Zg (Funktionsprototypen generieren)
ms.date: 11/04/2016
f1_keywords:
- /zg
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
ms.openlocfilehash: 684174cf46e644c22e072e3fa60f75f9434c7e54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315897"
---
# <a name="zg-generate-function-prototypes"></a>/Zg (Funktionsprototypen generieren)

Entfernt. Erstellt für jede in der Quelldatei definierte Funktion einen Funktionsprototyp, kompiliert die Quelldatei aber nicht.

## <a name="syntax"></a>Syntax

```
/Zg
```

## <a name="remarks"></a>Hinweise

Diese Compileroption ist nicht mehr verfügbar. Sie wurde in Visual C++ 2015 entfernt. Diese Seite ist für Benutzer von älteren Versionen von Visual C++ vorgesehen.

Der Funktionsprototyp beinhaltet den Rückgabedatentyp der Funktion und eine Liste der Argumenttypen. Die Liste der Argumenttypen wird anhand der Typen der formalen Parameter der Funktion erstellt. Alle in der Quelldatei bereits vorhandenen Funktionsprototypen werden ignoriert.

Die Liste der Prototypen wird in die Standardausgabe geschrieben. Mithilfe dieser Liste können Sie prüfen, ob die tatsächlichen und formalen Parameter einer Funktion kompatibel sind. Sie können die Liste speichern, indem Sie die Standardausgabe in eine Datei umleiten. Dann können Sie **#include** verwenden, um die Liste der Funktionsprototypen zu einem Bestandteil Ihrer Quelldatei zu machen. Dadurch wird der Compiler veranlasst, eine Argumenttypüberprüfung auszuführen.

Wenn Sie die **/Zg** -Option verwenden und Ihr Programm formale Parameter des Typs „struct“, „enum“ oder „union“ (oder Zeiger auf solche Typen) hat, muss die Deklaration für jeden „struct“-, „enum“- oder „union“-Typ einen Tagnamen haben. Im folgenden Beispiel ist der Tagname `MyStruct`.

```C
// Zg_compiler_option.c
// compile with: /Zg
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```

Die **/Zg** Option wurde in Visual Studio 2005 als veraltet markiert und wurde in Visual Studio 2015 entfernt. Der MSVC-Compiler wurde die Unterstützung für ältere, C-Stil Code entfernt. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
