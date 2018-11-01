---
title: Compilerfehler C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 58cf9867a9e36b304ab9da79084bc01dff453892
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462659"
---
# <a name="compiler-error-c2014"></a>Compilerfehler C2014

Präprozessorbefehl muss mit dem ersten beginnen.

Die `#` Anzeichen einer Präprozessordirektive muss das erste Zeichen in einer Zeile, das kein Leerzeichen ist.

Im folgende Beispiel wird die C2014 generiert:

```
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

Mögliche Lösung:

```
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```