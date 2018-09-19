---
title: Stack-Nutzung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 827a129c0b7a444cc5b48ba68a3e360712e1c08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721538"
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