---
title: Compilerfehler C3141 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3141
dev_langs:
- C++
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fda465b7cad2b46510b6f5e2dc4dc5d5fe82ecaf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038320"
---
# <a name="compiler-error-c3141"></a>Compilerfehler C3141

"Schnittstellenname": Schnittstellen unterstützen nur öffentliche Vererbung

Schnittstellen, die definiert, mit der [-Schnittstelle (oder __interface)](../../cpp/interface.md) Schlüsselwort nur öffentliche Vererbung unterstützt.

Im folgende Beispiel wird die C3141 generiert:

```
// C3141.cpp
__interface IBase {};
__interface IDerived1 : protected IBase {};  // C3141
__interface IDerived2 : private IBase {};    // C3141
```