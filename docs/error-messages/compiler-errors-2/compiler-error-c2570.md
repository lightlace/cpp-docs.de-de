---
title: Compilerfehler C2570 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5914af21ec780167c45334829a5d6517cf3662
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052977"
---
# <a name="compiler-error-c2570"></a>Compilerfehler C2570

'Bezeichner': Union kann keine Basisklasse haben.

Eine Union leitet sich von einer Klasse, Struktur oder Union. Dies ist nicht zulässig. Deklarieren Sie stattdessen den abgeleiteten Typ als eine Klasse oder Struktur.

Im folgende Beispiel wird die C2570 generiert:

```
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```