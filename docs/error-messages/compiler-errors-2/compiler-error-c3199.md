---
title: Compilerfehler C3199 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed917b3711f7f757b0a4ad89f0e6594ea1642a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027274"
---
# <a name="compiler-error-c3199"></a>Compilerfehler C3199

Ungültige Verwendung von Gleitkommapragmas: Ausnahmen werden in nicht dem precise-Modus nicht unterstützt

Die [Float_control](../../preprocessor/float-control.md) Pragma wurde verwendet, um das Modell für Gleitkommaausnahmen unter Geben Sie eine [/fp](../../build/reference/fp-specify-floating-point-behavior.md) andere Einstellung als **/fp: präzise**.

Im folgende Beispiel wird die C3199 generiert:

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```