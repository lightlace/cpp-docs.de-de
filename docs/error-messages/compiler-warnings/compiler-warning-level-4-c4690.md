---
title: Compilerwarnung (Stufe 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: c7facdde54b44ba2ce07db0447b251d7014f76c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324583"
---
# <a name="compiler-warning-level-4-c4690"></a>Compilerwarnung (Stufe 4) C4690

> \[ Emitidl (Pop)]: mehr POP-als Push-Vorgänge

## <a name="remarks"></a>Hinweise

Das [emitidl](../../windows/emitidl.md) -Attribut wurde einmal mehr vom Stapel abgerufen als in den Stapel verschoben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4690 generiert. Um dieses Problem zu beheben, stellen Sie sicher, dass das Attribut per pop ausgelesen wird, genau wie oft und solange es per Push übertragen wird.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
