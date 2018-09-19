---
title: Compilerfehler C2388 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b6bcec4f5f218a52981a7770f5fa6e600494d9a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114149"
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