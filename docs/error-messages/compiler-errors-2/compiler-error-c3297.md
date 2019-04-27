---
title: Compilerfehler C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: e4661119680dff34dfaa43fb9ce71bf97150a8bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222491"
---
# <a name="compiler-error-c3297"></a>Compilerfehler C3297

'Einschränkung_2': 'Einschränkung_1' kann nicht als Einschränkung verwendet werden, da 'Einschränkung_1' die Werteinschränkung aufweist.

Wertklassen sind versiegelt. Wenn eine Einschränkung eine Wertklasse ist, kann von ihr keine andere Einschränkung abgeleitet werden.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3297 generiert:

```
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```