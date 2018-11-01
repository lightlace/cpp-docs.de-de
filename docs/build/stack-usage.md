---
title: Verwendung von Stapeln
ms.date: 11/04/2016
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: 5ee9da50a03e1137ed6543cd349481148c9127d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452220"
---
# <a name="stack-usage"></a>Verwendung von Stapeln

Alle Speicher außerhalb der aktuellen Adresse der RSP gilt als flüchtige: das Betriebssystem und einen Debugger, kann dieser Arbeitsspeicher während einer Debugsitzung für Benutzer oder einem Interrupthandler überschreiben. RSP muss daher immer festgelegt werden, bevor Sie versuchen, das Lesen und Schreiben von Werten in einen Stapelrahmen.

Dieser Abschnitt beschreibt die Zuordnung an Stapelspeicher für lokale Variablen und die **Alloca** systeminterne.

- [Stapelreservierung](../build/stack-allocation.md)

- [Dynamische Parameterstapelbereichskonstruktion](../build/dynamic-parameter-stack-area-construction.md)

- [Funktionstypen](../build/function-types.md)

- [malloc-Ausrichtung](../build/malloc-alignment.md)

- [alloca](../build/alloca.md)

## <a name="see-also"></a>Siehe auch

[x64-Softwarekonventionen](../build/x64-software-conventions.md)