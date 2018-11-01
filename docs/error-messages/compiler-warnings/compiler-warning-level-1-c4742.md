---
title: Compilerwarnung (Stufe 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 00ac67fec3aafa5a259b5222bd6bb8654210fa61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436361"
---
# <a name="compiler-warning-level-1-c4742"></a>Compilerwarnung (Stufe 1) C4742

"Var" hat eine unterschiedliche Ausrichtung in "Datei1" und "Datei2": Anzahl und die Anzahl

Eine externe Variable, die auf die verwiesen wird, oder in zwei Dateien definiert wurde hat eine unterschiedliche Ausrichtung in diesen Dateien. Diese Warnung wird ausgegeben, wenn der Compiler feststellt, dass `__alignof` für die Variable im *"file1"* unterscheidet sich von `__alignof` für die Variable im *Datei2*. Dies kann verursacht werden, mithilfe von inkompatiblen Typen beim Deklarieren von Variablen in verschiedenen Dateien oder mit nicht übereinstimmenden `#pragma pack` in verschiedenen Dateien.

Um diese Warnung zu beheben, verwenden Sie die gleichen Typdefinition oder verwenden Sie unterschiedliche Namen für die Variablen.

Weitere Informationen finden Sie unter [Pack](../../preprocessor/pack.md) und [__alignof-Operator](../../cpp/alignof-operator.md).

## <a name="example"></a>Beispiel

Dies ist die erste Datei, die den Typ definiert.

```
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4742 generiert.

```
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```