---
title: Compilerfehler C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: 3ee2dc24dd2472be8b69a389df1cad77337abf90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368159"
---
# <a name="compiler-error-c2206"></a>Compilerfehler C2206

„function“: typedef kann nicht für die Definition einer Funktion verwendet werden.

Ein `typedef` -Element wird verwendet, um einen Funktionstyp zu definieren.

Das folgende Beispiel generiert C2206:

```
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```