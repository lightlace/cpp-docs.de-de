---
title: Compilerwarnung (Stufe 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d14a1902db4dcf2224ce6a58db120a81ebb5620f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327352"
---
# <a name="compiler-warning-level-1-c4326"></a>Compilerwarnung (Stufe 1) C4326

> der Rückgabetyp des '*Funktion*'muss'*type1*"anstelle von"*Typ2*"

## <a name="remarks"></a>Hinweise

Eine Funktion hat einen Typ zurückgegeben, außer *type1*. Verwenden Sie beispielsweise [/Za](../../build/reference/za-ze-disable-language-extensions.md), **main** hat keine zurückgegeben ein **Int**.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4326 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```