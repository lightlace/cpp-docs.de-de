---
title: Compilerfehler C2466 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d43ee9d09fba77db022177a06c6ebe95c65ff79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037839"
---
# <a name="compiler-error-c2466"></a>Compilerfehler C2466

ein Array von Konstanten Größe 0 kann nicht zugeordnet werden.

Ein Array ist reserviert oder mit Größe 0 (null) deklariert. Der Konstante Ausdruck für die Größe des Arrays muss eine ganze Zahl größer als 0 (null) sein. Eine Arraydeklaration mit einem Nullindex ist zulässig, nur für eine Klasse, Struktur oder union-Member und nur mit Microsoft-Erweiterungen ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Im folgende Beispiel wird die C2466 generiert:

```
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```