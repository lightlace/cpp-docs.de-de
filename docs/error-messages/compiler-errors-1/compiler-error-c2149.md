---
title: Compilerfehler C2149 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2149
dev_langs:
- C++
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38ebb710cc9f4d5f546c40d84909dbe23805f2f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094922"
---
# <a name="compiler-error-c2149"></a>Compilerfehler C2149

"Bezeichner": Die Breite des benannten Bitfelds muss größer als null (0) sein.

Nur nicht benannte Bitfelder können eine Breite von null (0) aufweisen.

Im folgenden Beispiel wird C2149 generiert:

```
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```