---
title: Compilerfehler C3198 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3198
dev_langs:
- C++
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbb91d6f7b3ef6b8204a5f8bfb753db98ab6f93d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023383"
---
# <a name="compiler-error-c3198"></a>Compilerfehler C3198

Ungültige Verwendung von Gleitkommapragmas: Fenv_access-Pragma wird nur im precise-Modus ausgeführt.

[Fenv_access](../../preprocessor/fenv-access.md) Pragma wurde verwendet, unter einer [/fp](../../build/reference/fp-specify-floating-point-behavior.md) andere Einstellung als **/fp: präzise**.

Im folgende Beispiel wird die C3198 generiert:

```
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```