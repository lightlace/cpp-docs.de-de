---
title: Compilerfehler C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 4d1cd510cda9957ced1d9dd5fd8fea267f39220d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507769"
---
# <a name="compiler-error-c3366"></a>Compilerfehler C3366

'Variable': statische Datenmember von verwalteten oder WinRTtypes muss innerhalb der Klassendefinition definiert werden

Sie haben versucht, auf einen statischen Member einer WinRT- oder .NET-Klasse oder -Schnittstelle außerhalb der Definition der Klasse oder Schnittstelle zu verweisen.

Der Compiler muss die vollständige Definition der Klasse kennen (um Metadaten nach einer Übergabe auszugeben) und erfordert statische Datenmember für die Initialisierung innerhalb der Klasse.

Beispielsweise generiert das folgende Beispiel C3366 und zeigt, wie Sie den Fehler beheben:

```
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
