---
title: /Zc:inline (unreferenzierte COMDAT entfernen)
ms.date: 03/01/2018
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: 6855773c6ec807a7488fa5604ddee7fd43983135
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441235"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (unreferenzierte COMDAT entfernen)

Entfernt unreferenzierte Funktionen oder Daten, die COMDATs sind oder nur eine interne Bindung haben. Wenn **/Zc: Inline** angegeben ist, wird der Compiler erfordert, dass Übersetzungseinheiten, die Inlinedaten oder Inlinefunktionen verwenden, auch die Definitionen für die Daten oder Funktionen enthalten müssen.

## <a name="syntax"></a>Syntax

> **/Zc:inline**[**-**]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: Inline** angegeben ist, wird der Compiler gibt keine Symbolinformationen für Unreferenzierte COMDAT-Funktionen oder Daten oder für Funktionen oder Daten, die nur eine internen Bindung haben. Diese Optimierung vereinfacht einen Teil der Aufgaben, die der Linker in Releasebuilds oder wenn die Linkeroption [/OPT: REF](../../build/reference/opt-optimizations.md) angegeben ist. Wenn der Compiler diese Optimierung durchführt, kann er die Größe der .obj-Datei deutlich verringern und Linkergeschwindigkeiten verbessern. Diese Compileroption ist nicht aktiviert, wenn Optimierungen deaktiviert sind ([/Od](../../build/reference/od-disable-debug.md)) oder wenn [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md) angegeben ist.

Diese Option ist standardmäßig deaktiviert (**/Zc:inline-**). Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option ermöglicht keine **/Zc: Inline**.

Wenn **/Zc: Inline** angegeben ist, wird der Compiler erzwingt die C ++ 11-Anforderung, die alle Funktionen deklariert `inline` muss eine Definition in derselben Übersetzungseinheit verfügen, wenn sie verwendet werden. Wenn die Option nicht angegeben ist, handelt es sich bei der Microsoft-Compiler lässt nicht konformen Code, die darin deklarierte Funktionen aufruft `inline` , auch wenn keine Definition sichtbar ist. Weitere Informationen finden Sie unter „C++11-Standard“ in den Abschnitten 3.2 und 7.1.2. Diese Compileroption wurde in Visual Studio 2013 Update 2 eingeführt.

Verwenden der **/Zc: Inline** option Update nicht konformen Code.

Dieses Beispiel zeigt, wie nicht konforme einer inlinefunktionsdeklaration ohne Definition noch kompiliert und verknüpft wird, wenn der Standardwert **/Zc:inline-** Option wird verwendet:

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n");
}

void Example::normal_call() {
   printf("normal_call was called.\n");
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

Wenn **/Zc: Inline** aktiviert ist, verursacht derselbe code einen [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) Fehler, da der Codetext nicht-inline-für Compiler keine ist `Example::inline_call` in example.obj ausgibt. Das führt dazu, dass der Nicht-Inlineaufruf in `main` ein nicht definiertes externe Symbol referenziert.

Zur Fehlerbehebung können Sie das Schlüsselwort `inline` aus der Deklaration von `Example::inline_call` entfernen, die Definition von `Example::inline_call` in die Headerdatei verschieben oder die Implementierung von `Example` in main.cpp verschieben. Im nächsten Beispiel wird die Definition in die Headerdatei verschoben, in der sie für jeden Aufrufer sichtbar ist, der den Header enthält.

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n");
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n");
   inline_call();
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Sprache** Eigenschaftenseite.

1. Ändern der **entfernt Unreferenzierte Code und Daten** -Eigenschaft, und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
