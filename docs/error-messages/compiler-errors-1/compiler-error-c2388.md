---
title: Compilerfehler C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 62afcb1fafc19d3d61a86f2fbc10cb99e095afc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393661"
---
# <a name="compiler-error-c2388"></a>Compilerfehler C2388

'Symbol': ein Symbol kann nicht mit beiden __declspec(appdomain) deklariert werden und \__declspec(process)

Die Modifizierer `appdomain` und `process` `__declspec` können nicht für dasselbe Symbol verwendet werden. Der Speicher für eine Variable ist pro Prozess- oder Anwendungsdomäne vorhanden.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).

Im folgenden Beispiel wird C2388 generiert:

```
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```