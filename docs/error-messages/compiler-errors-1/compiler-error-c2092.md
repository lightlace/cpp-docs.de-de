---
title: Compilerfehler C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: d3d0b0e62fbc5f8ad90b3fee5fe39c6bdaba7c2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376004"
---
# <a name="compiler-error-c2092"></a>Compilerfehler C2092

Elementtyp des Arrays "Arrayname" kann keine Funktion sein.

Arrays aus Funktionen sind nicht zulässig. Verwenden Sie ein Array von Zeigern auf Funktionen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2092 generiert:

```
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

## <a name="example"></a>Beispiel

Mögliche Lösung:

```
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```