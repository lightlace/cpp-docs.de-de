---
title: Compilerfehler C3293
ms.date: 07/21/2017
f1_keywords:
- C3293
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
ms.openlocfilehash: 84d539722474d5f5dfffe1f6fe121bb7349ba131
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548208"
---
# <a name="compiler-error-c3293"></a>Compilerfehler C3293

'Accessor': Verwenden Sie 'default', um auf die Standardeigenschaft (Indexer) der 'Typ'-Klasse zuzugreifen.

Auf eine indizierte Eigenschaft wurde nicht ordnungsgemäß zugegriffen.  Finden Sie unter [Vorgehensweise: Verwenden von Eigenschaften in C++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) für Weitere Informationen.

**Visual Studio 2017 und höher**: In Visual Studio 2015 und frühere Versionen der Compiler in einigen Fällen eine Standardeigenschaft als einen Standardindexer falsch kategorisiert. Es war möglich das Problem zu umzugehen, indem mithilfe des „default“-Bezeichners auf die Eigenschaft zugegriffen wurde. Die Lösung selbst wurde problematisch, nachdem default als Schlüsselwort in C++11 eingeführt wurde. Aus diesem Grund wurden in Visual Studio 2017 Fehler behoben, die die Problemumgehung erforderten, und der Compiler löst jetzt einen Fehler aus, wenn „default“ verwendet wird, um auf die Standardeigenschaft für eine Klasse zuzugreifen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3293 in Visual Studio 2015 und früher.

```
// C3293.cpp
// compile with: /clr /c
using namespace System;
ref class IndexerClass {
public:
   // default indexer
   property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};

int main() {
   IndexerClass ^ ic = gcnew IndexerClass;
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier

   String ^s = "Hello";
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier
   Console::WriteLine(wc2);
}
```