---
title: Compilerfehler C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 21658a659468a6e2a0d911af70eefdaed320446c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745056"
---
# <a name="compiler-error-c2388"></a>Compilerfehler C2388

' Symbol ': ein Symbol kann nicht mit __declspec (AppDomain) und \__declspec (Prozess) deklariert werden.

Die Modifizierer `appdomain` und `process` `__declspec` können nicht für dasselbe Symbol verwendet werden. Der Speicher für eine Variable ist pro Prozess- oder Anwendungsdomäne vorhanden.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).

Im folgenden Beispiel wird C2388 generiert:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
