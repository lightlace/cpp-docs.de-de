---
title: /Zc:inline (unreferenzierte COMDAT entfernen)
ms.date: 09/05/2019
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: 42791b2e337fb9a9724a165145e757152b8d679d
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518243"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (unreferenzierte COMDAT entfernen)

Entfernt nicht referenzierte Daten oder Funktionen, die COMDATs sind oder nur über eine interne Verknüpfung verfügen. Unter **/Zc: Inline**gibt der Compiler an, dass Übersetzungseinheiten mit Inline Daten oder Funktionen auch ihre Definitionen einschließen müssen.

## <a name="syntax"></a>Syntax

> **/Zc:inline**[ **-** ]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: Inline** angegeben wird, gibt der Compiler keine Symbol Informationen für nicht referenzierte COMDAT-Funktionen oder-Daten aus. Oder für Daten oder Funktionen, die nur über interne Verknüpfungen verfügen. Diese Optimierung vereinfacht einige der Aufgaben, die der Linker in Releasebuilds durchführt, oder wenn Sie die Linkeroption [/OPT: Ref](opt-optimizations.md) angeben. Diese Compileroptimierung kann die Größe der obj-Datei erheblich reduzieren und die Linker-Geschwindigkeit verbessern. Die-Compileroption ist nicht aktiviert, wenn Sie Optimierungen deaktivieren ([/od](od-disable-debug.md)). Oder, wenn Sie [/GL (Optimierung des ganzen Programms)](gl-whole-program-optimization.md)angeben.

Standardmäßig ist diese Option deaktiviert ( **/Zc: Inline-** ) in Befehlszeilenbuilds. Die [/permissive-](permissive-standards-conformance.md) -Option aktiviert **/Zc: Inline**nicht. In MSBuild-Projekten wird die Option von den **Konfigurations Eigenschaften** > **CC++ /**  > **Sprache** festgelegt > **Entfernen von nicht referenzierten Code und der Daten** Eigenschaft, die standardmäßig auf " **Yes** " festgelegt ist.

Wenn **/Zc: Inline** angegeben ist, erzwingt der Compiler die Anforderung c++ 11, dass für alle Funktionen, die deklariert wurden `inline` eine Definition in derselben Übersetzungseinheit verfügbar sein muss, wenn Sie verwendet werden. Wenn die Option nicht angegeben wird, lässt der Microsoft-Compiler nicht kompatiblen Code zu, der Funktionen aufruft, die `inline` deklariert sind, auch wenn keine Definition sichtbar ist. Weitere Informationen finden Sie unter „C++11-Standard“ in den Abschnitten 3.2 und 7.1.2. Diese Compileroption wurde in Visual Studio 2013 Update 2 eingeführt.

Aktualisieren Sie den nicht kompatiblen Code, um die **/Zc: Inline** -Option zu verwenden.

Dieses Beispiel zeigt, wie die nicht kompatible Verwendung einer Inline Funktionsdeklaration ohne Definition weiterhin kompiliert und verknüpft wird, wenn die standardmäßige **/Zc: Inline-** Option verwendet wird:

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

int main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

Wenn **/Zc: Inline** aktiviert ist, verursacht derselbe Code einen [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) -Fehler, da der Compiler keinen nicht Inline-Code Körper für `Example::inline_call` in "example. obj" ausgibt. Dies bewirkt, dass der nicht-Inline-Aufrufe in `main` auf ein nicht definiertes externes Symbol verweist.

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

int main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++ C/**  > **Sprache** aus.

1. Ändern Sie die Eigenschaft **nicht referenzierten Code und die Daten entfernen** , und klicken Sie dann auf **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
