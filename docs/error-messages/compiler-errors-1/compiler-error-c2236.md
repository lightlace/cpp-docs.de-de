---
title: Compilerfehler C2236 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2236
dev_langs:
- C++
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fba2f795c3b786e82331a4b14f2c4530731db64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053685"
---
# <a name="compiler-error-c2236"></a>Compilerfehler C2236

Unerwartetes Token 'Bezeichner'. Haben Sie ein ';' vergessen?

Der Bezeichner wurde bereits als Typ definiert und kann nicht durch einen benutzerdefinierten Typ überschrieben werden.

Das folgende Beispiel generiert C2236:

```
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```