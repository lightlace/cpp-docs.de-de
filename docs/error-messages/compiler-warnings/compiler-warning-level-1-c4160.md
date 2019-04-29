---
title: Compilerwarnung (Stufe 1) C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: 988c1fcbe0826582dceaa527811c688711fd8906
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391841"
---
# <a name="compiler-warning-level-1-c4160"></a>Compilerwarnung (Stufe 1) C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>Pragma (Pop,...): zuvor per push abgelegten Bezeichner wurde nicht gefunden "*Bezeichner*"

## <a name="remarks"></a>Hinweise

Eine Pragma-Anweisung im Quellcode versucht, einen Bezeichner per Pop auszulesen, der nicht per Push veröffentlicht wurde. Um diese Warnung zu vermeiden, achten Sie darauf, dass der ausgelesene Bezeichner ordnungsgemäß gepusht wurde.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4160 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```