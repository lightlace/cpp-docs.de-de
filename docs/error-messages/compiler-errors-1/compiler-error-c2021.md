---
title: Compilerfehler C2021 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31169c59ba9731d8eda52f22644294b8bb680bf2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101988"
---
# <a name="compiler-error-c2021"></a>Compilerfehler C2021

Exponentwert erwartet und nicht „character“.

Das Zeichen als Exponent einer Gleitkommakonstanten verwendet ist keine gültige Zahl. Achten Sie darauf, dass Sie einen Exponenten zu verwenden, der im Bereich befindet.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2021 generiert:

```
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>Beispiel

Mögliche Lösung:

```
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```