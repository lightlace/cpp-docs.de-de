---
title: Compilerfehler C3219 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3219
dev_langs:
- C++
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f60a17d257505752f9d2c791365f537fa02ffc2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022580"
---
# <a name="compiler-error-c3219"></a>Compilerfehler C3219

"param": Der generische Parameter kann nicht von mehreren Nichtschnittstellen eingeschränkt werden: "Klasse".

Es ist nicht zulässig, einen generischen Parameter durch zwei oder mehr verwaltete Klassen einzuschränken.

Im folgenden Beispiel wird C3219 generiert:

```
// C3219.cpp
// compile with: /clr
ref class A {};
ref class B {};

generic <class T>
where T : A, B
ref class E {};   // C3219
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```
// C3219b.cpp
// compile with: /clr /c
ref class A {};

interface struct C {};

generic <class T>
where T : A
ref class E {};
```