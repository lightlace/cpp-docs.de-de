---
title: Compilerfehler C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: 0166cce6011017b8a18821666083f7c47f58b7a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302539"
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