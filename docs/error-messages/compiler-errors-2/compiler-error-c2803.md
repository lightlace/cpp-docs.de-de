---
title: Compilerfehler C2803 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7885735ebad1ff90afaf4ba8eaf6dfca9f3e0ab3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027036"
---
# <a name="compiler-error-c2803"></a>Compilerfehler C2803

'Operator Operator' muss mindestens einen formalen Parameter des Klassentyps haben.

Der überladene Operator hat einen Parameter vom Klassentyp.

Müssen Sie mindestens einen Parameter als Verweis (nicht mit Zeigern, sondern Verweise) oder anhand des Werts zu schreiben können übergeben "ein < b" (ein und b von Typklasse-A).

Wenn beide Parameter Zeiger ein reiner Vergleich der Zeigeradressen werden und die benutzerdefinierte Konvertierung wird nicht verwendet.

Im folgende Beispiel wird die C2803 generiert:

```
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```