---
title: Compilerfehler C2345 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2345
dev_langs:
- C++
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb20a744c2a8ef67901da10c4933bc38402c710f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048122"
---
# <a name="compiler-error-c2345"></a>Compilerfehler C2345

align(wert: ungültiger Ausrichtungswert

Sie haben einen Wert an das Schlüsselwort [align](../../cpp/align-cpp.md) übergeben, er außerhalb des zulässigen Bereichs liegt.

Durch den folgenden Code wird der Fehler C2345 ausgelöst:

```
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```