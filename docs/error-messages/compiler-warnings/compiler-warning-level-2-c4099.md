---
title: Compilerwarnung (Stufe 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: d685f1f40826b975623dbedc2ba8115c6b3edc45
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052180"
---
# <a name="compiler-warning-level-2-c4099"></a>Compilerwarnung (Stufe 2) C4099

"Bezeichner": der Typname wird zuerst mithilfe von "objecttype1" angezeigt und wird jetzt mit "objecttype2" angezeigt.

Ein-Objekt, das als-Struktur deklariert ist, wird als-Klasse definiert, oder ein Objekt, das als Klasse deklariert wird, wird als Struktur definiert. Der Compiler verwendet den Typ, der in der Definition angegeben ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4099 generiert.

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```