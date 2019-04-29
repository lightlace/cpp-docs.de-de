---
title: Compilerwarnung (Stufe 1) C4772
ms.date: 11/04/2016
f1_keywords:
- C4772
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
ms.openlocfilehash: 95243ab66d5d0296e1c316ff8dde7add75a030cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385458"
---
# <a name="compiler-warning-level-1-c4772"></a>Compilerwarnung (Stufe 1) C4772

> \#Import auf einen Typ aus einer fehlenden Typbibliothek verwiesen; "*fehlende Typ*" als Platzhalter verwendet

Eine Typbibliothek mit verwiesen wurde, wird die [#import](../../preprocessor/hash-import-directive-cpp.md) Richtlinie. Die Typbibliothek enthalten einen Verweis auf eine andere Typbibliothek, die nicht in referenziert wurde `#import`. Diese anderen TLB-Datei wurde vom Compiler nicht gefunden.

Beachten Sie, dass der Compiler Typbibliotheken nicht in verschiedenen Verzeichnissen finden, und wird bei Verwendung der [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md) -Compileroption verwenden, um diese Verzeichnisse angeben. Wenn Sie möchten, dass der Compiler Typbibliotheken in verschiedenen Verzeichnissen finden, fügen Sie diese Verzeichnisse zu PATH-Umgebungsvariablen hinzu.

Standardmäßig wird diese Warnung als Fehler ausgegeben. C4772 kann nicht mit/W0 unterdrückt werden.

## <a name="example"></a>Beispiel

Dies ist die erste Typbibliothek erforderlich, um C4772 zu reproduzieren.

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

Dies ist die zweite Typbibliothek erforderlich, um C4772 zu reproduzieren.

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

Im folgende Beispiel wird die C4772 generiert:

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```