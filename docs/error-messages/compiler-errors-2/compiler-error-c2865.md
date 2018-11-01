---
title: Compilerfehler C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: e95714f7a10c1c25562e8b12025ede486e66cff8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532735"
---
# <a name="compiler-error-c2865"></a>Compilerfehler C2865

'Funktion': Unzulässiger Vergleich für Handle_or_pointer

Sie können Verweise auf Vergleichen [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) oder verwaltet von Verweistypen, die nur auf Gleichheit zu überprüfen, ob sie auf das gleiche Objekt (==) oder auf andere Objekte verweisen (! =).

Sie können nicht verglichen werden für die Sortierung, da die .NET Runtime verwaltete Objekte zu jedem Zeitpunkt verschoben werden kann das Ergebnis des Tests ändern.