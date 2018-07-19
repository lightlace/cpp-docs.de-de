---
title: Compilerwarnung (Stufe 4) C4690 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/03/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4690
dev_langs:
- C++
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04fb68bdab762f0f541849fad1568caff836b623
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853321"
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
