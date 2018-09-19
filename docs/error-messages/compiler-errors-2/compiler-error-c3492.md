---
title: Compilerfehler C3492 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3492
dev_langs:
- C++
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54b3689a6ee565788e2a469a8321727a9fdd822f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089215"
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