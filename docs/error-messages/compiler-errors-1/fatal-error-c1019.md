---
title: Schwerwiegender Fehler C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: f33139393f7f6225edf0c4b3f992b93d35bd6afa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756915"
---
# <a name="fatal-error-c1019"></a>Schwerwiegender Fehler C1019

Unerwartetes #else

Die `#else` -Direktive befindet sich außerhalb eines `#if`-, `#ifdef`- oder `#ifndef` -Konstrukts. Verwenden Sie `#else` nur innerhalb eines dieser Konstrukte.

Im folgenden Beispiel wird C1019 generiert:

```cpp
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

Mögliche Lösung:

```cpp
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```
