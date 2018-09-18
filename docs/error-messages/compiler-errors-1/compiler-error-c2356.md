---
title: Compilerfehler C2356 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2356
dev_langs:
- C++
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfad1703b36e1cd995207d35b99b323c883f828
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065412"
---
# <a name="compiler-error-c2356"></a>Compilerfehler C2356

Initialisierungssegment darf während der Übersetzungseinheit nicht geändert.

Mögliche Ursachen:

- `#pragma init_seg` vor dem Code zur Initialisierung von segment

- `#pragma init_seg` durch eine andere voranstehen `#pragma init_seg`

Verschieben Sie den Initialisierungscode für Segment an den Anfang des Moduls. Verschieben sie mehrere Bereiche initialisiert werden müssen, die Module zu trennen.

Im folgende Beispiel wird die C2356 generiert:

```
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```