---
title: Compilerwarnung (Stufe 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: 09ea9e2963735c1e011e25b42b04ad6d67d084a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349814"
---
# <a name="compiler-warning-level-2-c4099"></a>Compilerwarnung (Stufe 2) C4099

'Bezeichner': Typ den zuerst mithilfe von "Objekttyp1 ' und jetzt mit"%objecttype2"

Ein Objekt, das als eine Struktur deklariert wird als eine Klasse definiert, oder ein Objekt, das als eine Klasse deklariert wird als Struktur definiert. Der Compiler verwendet den Typ in der Definition.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4099 generiert.

```
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```