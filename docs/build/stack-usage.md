---
title: Verwendung des Stapels | Microsoft Docs
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
ms.openlocfilehash: b6f711636089a6f2966002002220aac88cebe17a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379857"
---
# <a name="stack-usage"></a>Verwendung von Stapeln
Alle Speicher außerhalb der aktuellen Adresse des RSP gilt volatile: das Betriebssystem oder ein Debugger kann diesen Arbeitsspeicher während einer Debugsitzung für Benutzer oder ein nicht maskierbarer Interrupt überschreiben. Daher muss RSP immer festgelegt werden, bevor Sie versuchen, das Lesen und Schreiben von Werten in einen Stapelrahmen.  
  
 Dieser Abschnitt beschreibt die Zuordnung von Stapelspeicher für lokale Variablen und die **Alloca** systeminterne.  
  
-   [Stapelreservierung](../build/stack-allocation.md)  
  
-   [Dynamische Parameterstapelbereichskonstruktion](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [Funktionstypen](../build/function-types.md)  
  
-   [malloc-Ausrichtung](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)