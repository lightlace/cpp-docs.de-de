---
title: Compilerfehler C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: 53dd22368aee5e0de9eca1349eb4d7dd3ed1c570
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485006"
---
# <a name="compiler-error-c3492"></a>Compilerfehler C3492

'var': Ein Member einer anonymen Union kann nicht erfasst werden.

Sie können ein Member einer unbenannten Union nicht erfassen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Weisen Sie der Union einen Namen zu, und übergeben Sie die vollständige Union-Struktur an die Erfassungsliste des Lambdaausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3492 generiert, da ein Member einer anonymen Union erfasst wird:

```
// C3492a.cpp

int main()
{
   union
   {
      char ch;
      int x;
   };

   ch = 'y';
   [&x](char ch) { x = ch; }(ch); // C3492
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3492 behoben, indem der Union ein Name zugewiesen und die vollständige Union-Struktur an die Erfassungsliste des Lambdaausdrucks übergeben wird.

```
// C3492b.cpp

int main()
{
   union
   {
      char ch;
      int x;
   } u;

   u.ch = 'y';
   [&u](char ch) { u.x = ch; }(u.ch);
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)