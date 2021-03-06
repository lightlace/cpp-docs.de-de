---
title: /Gh (_penter-Hookfunktion aktivieren)
ms.date: 11/04/2016
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: bf7734a7b81c9550c060d43c2eabf5cb05332407
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292580"
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (_penter-Hookfunktion aktivieren)

Bewirkt, dass einen Aufruf der `_penter` Funktion am Anfang jeder Methode oder Funktion.

## <a name="syntax"></a>Syntax

```
/Gh
```

## <a name="remarks"></a>Hinweise

Die `_penter` Funktion ist nicht Teil einer Bibliothek, und es ist Ihre Aufgabe, geben Sie eine Definition für `_penter`.

Es sei denn, Sie planen, die explizit aufrufen `_penter`, Sie müssen sich nicht um einen Prototyp bereitzustellen. Die Funktion muss angezeigt werden, als ob es den folgenden Prototyp hatte und Fördern Sie den Inhalt aller Register auf den Eintrag und pop die unveränderten Inhalt beim Beenden müssen:

```
void __declspec(naked) __cdecl _penter( void );
```

Diese Deklaration ist nicht für 64-Bit-Projekte verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Beispiel

Der folgende code ist bei der Kompilierung mit **/GH**, zeigt, wie `_penter` wird zweimal aufgerufen, einmal beim Eingeben der Funktion `main` und einmal bei der Eingabe der Funktion `x`.

```cpp
// Gh_compiler_option.cpp
// compile with: /Gh
// processor: x86
#include <stdio.h>
void x() {}

int main() {
   x();
}

extern "C" void __declspec(naked) __cdecl _penter( void ) {
   _asm {
      push eax
      push ebx
      push ecx
      push edx
      push ebp
      push edi
      push esi
    }

   printf_s("\nIn a function!");

   _asm {
      pop esi
      pop edi
      pop ebp
      pop edx
      pop ecx
      pop ebx
      pop eax
      ret
    }
}
```

```Output
In a function!
In a function!
```

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
