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
ms.openlocfilehash: f0c0d9a4e5e5f52d239f1a8591006b3d9e369778
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740114"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (unreferenzierte COMDAT entfernen)

Entfernt unreferenzierte Funktionen oder Daten, die COMDATs sind oder nur eine interne Bindung haben. Wenn **/Zc: Inline** angegeben wird, erfordert der Compiler, dass Übersetzungseinheiten, die Inline Daten oder Inline Funktionen verwenden, auch die Definitionen für die Daten oder Funktionen enthalten müssen.

## <a name="syntax"></a>Syntax

> **/Zc:inline**[ **-** ]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: Inline** angegeben wird, gibt der Compiler keine Symbol Informationen für nicht referenzierte COMDAT-Funktionen oder-Daten oder für Funktionen oder Daten aus, die nur intern verknüpft sind. Diese Optimierung vereinfacht einen Teil der Arbeit, die vom Linker in Releasebuilds ausgeführt wird, oder wenn die Linkeroption [/OPT: Ref](opt-optimizations.md) angegeben wird. Wenn der Compiler diese Optimierung durchführt, kann er die Größe der .obj-Datei deutlich verringern und Linkergeschwindigkeiten verbessern. Diese Compileroption ist nicht aktiviert, wenn Optimierungen deaktiviert sind ([/od](od-disable-debug.md)) oder wenn [/GL (gesamte Programm Optimierung)](gl-whole-program-optimization.md) angegeben wird.

Standardmäßig ist diese Option deaktiviert ( **/Zc: Inline-** ) in Befehlszeilenbuilds. Die [/permissive-](permissive-standards-conformance.md) -Option aktiviert **/Zc: Inline**nicht. In MSBuild-Projekten wird die Option von den **Konfigurations Eigenschaften** >  > **C/C++** **Sprache** > **Entfernen nicht referenzierter Code und Daten** Eigenschaft festgelegt, die auf **Ja** festgelegt ist. vorgegebene.

Wenn **/Zc: Inline** angegeben ist, erzwingt der Compiler die c++ 11-Anforderung, dass alle `inline` deklarierten Funktionen über eine Definition verfügen müssen, die in derselben Übersetzungseinheit verfügbar ist, wenn Sie verwendet werden. Wenn die Option nicht angegeben wird, lässt der Microsoft-Compiler nicht kompatiblen Code zu, der Funktionen aufruft `inline` , die auch dann deklariert werden, wenn keine Definition sichtbar ist. Weitere Informationen finden Sie unter „C++11-Standard“ in den Abschnitten 3.2 und 7.1.2. Diese Compileroption wurde in Visual Studio 2013 Update 2 eingeführt.

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

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

Wenn **/Zc: Inline** aktiviert ist, verursacht derselbe Code einen [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) -Fehler, da der Compiler keinen nicht Inline-Code Körper für `Example::inline_call` in example. obj ausgibt. Das führt dazu, dass der Nicht-Inlineaufruf in `main` ein nicht definiertes externe Symbol referenziert.

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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++C/**  > Sprache aus.

1. Ändern Sie die Eigenschaft **nicht referenzierten Code und die Daten entfernen** , und klicken Sie dann auf **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
