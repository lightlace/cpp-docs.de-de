---
title: Compilerfehler C2377
ms.date: 11/04/2016
f1_keywords:
- C2377
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
ms.openlocfilehash: b4789469fe27dafb2fb13bf3db085958db8d1478
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528764"
---
# <a name="compiler-error-c2377"></a>Compilerfehler C2377

'Bezeichner': Neudefinition. Typdefinition kann nicht mit einem anderen Symbol überladen werden.

Ein `typedef` -Bezeichner wird neu definiert.

Im folgenden Beispiel wird C2377 generiert:

```
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```