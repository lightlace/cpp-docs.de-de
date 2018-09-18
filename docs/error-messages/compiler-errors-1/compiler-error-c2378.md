---
title: Compilerfehler C2378 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2378
dev_langs:
- C++
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5aa4b8ecef6be2149132c9ccf533285cd0bb7f7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021823"
---
# <a name="compiler-error-c2378"></a>Compilerfehler C2378

"Bezeichner": Neudefinition; Symbol kann nicht mit typedef überladen werden

Der Bezeichner wurde als eine `typedef`neu definiert.

Im folgenden Beispiel wird C2378 generiert:

```
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```