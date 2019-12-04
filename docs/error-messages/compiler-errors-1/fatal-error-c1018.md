---
title: Schwerwiegender Fehler C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 3273288f1d60fad840fd8e9c459ce5d209ddb6a4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756928"
---
# <a name="fatal-error-c1018"></a>Schwerwiegender Fehler C1018

Unerwartetes #elif

Die `#elif` -Direktive befindet sich außerhalb eines `#if`-, `#ifdef`- oder `#ifndef` -Konstrukts. Verwenden Sie `#elif` nur innerhalb eines dieser Konstrukte.

Im folgenden Beispiel wird C1018 generiert:

```cpp
// C1018.cpp
#elif      // C1018
#endif

int main() {}
```

Mögliche Lösung:

```cpp
// C1018b.cpp
#if 1
#elif
#endif

int main() {}
```
