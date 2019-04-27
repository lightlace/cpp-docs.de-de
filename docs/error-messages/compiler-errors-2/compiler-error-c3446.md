---
title: Compilerfehler C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 8145e0cdd97022ebdcc1a7ce38c8860a005945b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182443"
---
# <a name="compiler-error-c3446"></a>Compilerfehler C3446

>"*Klasse*": ein standardmemberinitialisierer ist für einen Member einer Wertklasse unzulässig

In Visual Studio 2015 und früher, ließ der Compiler einen Standardmember-Initialisierer für einen Member einer Wertklasse zu, ignorierte diesen aber. Standardinitialisierung einer Wertklasse initialisiert die Elemente immer auf null; ein Standardkonstruktor ist nicht zulässig. In Visual Studio 2017 lösen Standardmember-Initialisierer einen Compilerfehler aus, wie im folgenden Beispiel gezeigt:

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3446 in Visual Studio 2017 und höher generiert:

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

Um den Fehler zu beheben, entfernen Sie den Initialisierer:

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```

