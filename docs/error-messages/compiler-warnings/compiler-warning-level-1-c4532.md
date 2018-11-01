---
title: Compilerwarnung (Stufe 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: bcadf31eda079ebb8ea7a496efe4c945e16b1ab7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622844"
---
# <a name="compiler-warning-level-1-c4532"></a>Compilerwarnung (Stufe 1) C4532

"continue": Aussprung aus __finally/finally-Block hat ein undefiniertes Verhalten während der Abbruchbehandlung

Der Compiler hat festgestellt, eines der folgenden Schlüsselwörter:

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

verursacht einen Sprung aus einem [__finally](../../cpp/try-finally-statement.md) oder [schließlich](../../dotnet/finally.md) Block bei nicht ordnungsgemäßer Beendigung.

Wenn eine Ausnahme tritt auf, und zwar während der Ausführung der Beendigungshandler im Stapel entladen wird (die `__finally` oder finally-Blöcken), und Ihr Code von springt eine `__finally` blockiert werden, bevor die `__finally` Block beendet, das Verhalten nicht definiert ist. Steuerelement möglicherweise nicht an den entladenen Code zurück, damit die Ausnahme nicht ordnungsgemäß verarbeitet werden kann.

Wenn Sie von wechseln müssen eine **__finally** blockieren, überprüfen Sie zunächst für die nicht ordnungsgemäße Beendigung.

Im folgende Beispiel wird die C4532 generiert. einfach kommentieren Sie die Jump-Anweisungen, um Warnungen aufzulösen.

```
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```