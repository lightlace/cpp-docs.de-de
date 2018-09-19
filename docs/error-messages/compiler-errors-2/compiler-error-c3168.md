---
title: Compilerfehler C3168 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3168
dev_langs:
- C++
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2a70af70af5b31ef9a3bf2fe939eef28783369a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106453"
---
# <a name="compiler-error-c3168"></a>Compilerfehler C3168

'Typ': Ungültiger zugrunde liegender Typ für Enumeration

Die zugrunde liegende Geben Sie bei der `enum` Typ war ungültig. Der zugrunde liegende Typ muss es sich um einen ganzzahligen C++-Typ oder einen entsprechenden CLR-Typ sein.

Im folgende Beispiel wird die C3168 generiert:

```
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
