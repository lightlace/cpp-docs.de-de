---
title: Compilerfehler C2092 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2092
dev_langs:
- C++
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a0b8f65f58ffe65abee0f15eb511f7857657597
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072484"
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