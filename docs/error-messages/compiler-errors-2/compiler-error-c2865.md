---
title: Compilerfehler C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: 38b7dd86a57c3cd89811c6489e51fb4271fd7b79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165145"
---
# <a name="compiler-error-c2865"></a>Compilerfehler C2865

'Funktion': Unzulässiger Vergleich für Handle_or_pointer

Sie können Verweise auf Vergleichen [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md) oder verwaltet von Verweistypen, die nur auf Gleichheit zu überprüfen, ob sie auf das gleiche Objekt (==) oder auf andere Objekte verweisen (! =).

Sie können nicht verglichen werden für die Sortierung, da die .NET Runtime verwaltete Objekte zu jedem Zeitpunkt verschoben werden kann das Ergebnis des Tests ändern.