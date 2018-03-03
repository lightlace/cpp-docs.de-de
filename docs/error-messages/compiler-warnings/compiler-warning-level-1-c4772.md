---
title: Compilerwarnung (Stufe 1) C4772 | Microsoft Docs
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C4772
dev_langs:
- C++
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 631cd4f872c7b8912b791417c04f6c6e9e056bdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4772"></a>Compilerwarnung (Stufe 1) C4772

> \#Import auf einen Typ aus einer fehlenden Typbibliothek verwiesen wird; "*fehlende Typ*" als Platzhalter verwendet

Eine Typbibliothek verwiesen wurde, mit der [#import](../../preprocessor/hash-import-directive-cpp.md) Richtlinie. Die Typbibliothek enthielt jedoch einen Verweis auf eine andere Typbibliothek, die nicht mit verwiesen wurde `#import`. Diese TLB-Datei wurde vom Compiler nicht gefunden.

Beachten Sie, dass der Compiler keine Typbibliotheken in verschiedenen Verzeichnissen findet bei Verwendung der [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md) -Compileroption dieser Verzeichnisse angeben. Wenn Sie den Compiler an, in verschiedenen Verzeichnissen Typbibliotheken suchen möchten, fügen Sie dieser Verzeichnisse hinzu PATH-Umgebungsvariable.

Standardmäßig wird diese Warnung als Fehler ausgegeben. C4772 kann nicht mit/W0 unterdrückt werden.

## <a name="example"></a>Beispiel

Dies ist die erste Typbibliothek zum Reproduzieren von C4772 erforderlich sind.

```IDL
// c4772a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C4772aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]
   enum E_C4772a
   {
      one, two, three
   };
};
```

Dies ist die zweite Typbibliothek zum Reproduzieren von C4772 erforderlich sind.

```IDL
// c4772b.idl
// post-build command: del /f C4772a.tlb
// C4772a.tlb is available when c4772b.tlb is built
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4772bLib
{
   importlib ("c4772a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4772b
   {
      enum E_C4772a e;
   };
};
```

Im folgenden Beispiel wird C4772 generiert:

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```