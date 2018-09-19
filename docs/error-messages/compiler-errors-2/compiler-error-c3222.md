---
title: Compilerfehler C3222 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30231f74b379cd9d69806fbd4b49ba0cb55ad871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048317"
---
# <a name="compiler-error-c3222"></a>Compilerfehler C3222

'Parameter': Für Memberfunktionen eines verwalteten oder WinRT-Typs oder generische Funktionen können keine Standardargumente deklariert werden.

Es ist nicht zulässig, einen Methodenparameter mit einem Standardargument zu deklarieren. Eine überladene Form der Methode ist eine Möglichkeit, dieses Problem zu umgehen. Das heißt, dass Sie eine Methode mit demselben Namen ohne Parameter definieren und anschließend die Variable im Methodentext initialisieren.

Im folgenden Beispiel wird C3222 generiert:

```
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
