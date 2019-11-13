---
title: Compilerwarnung (Stufe 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: 30e2ecb1d5e0de290c028cdfb53c7df831a732b4
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966458"
---
# <a name="compiler-warning-level-1-c4377"></a>Compilerwarnung (Stufe 1) C4377

Native Typen sind standardmäßig privat. -d1PrivateNativeTypes "ist veraltet

In früheren Versionen waren Native Typen in Assemblys standardmäßig öffentlich, und eine interne, nicht dokumentierte Compileroption ( **/d1PrivateNativeTypes**) wurde verwendet, um Sie als privat festzulegen.

Alle Typen, Native und CLR, sind jetzt standardmäßig in einer Assembly privat, sodass **/d1PrivateNativeTypes** nicht mehr benötigt wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4377 generiert.

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```