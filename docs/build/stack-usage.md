---
title: Verwendung des Stapels | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7a74abff7a2971fe66fa2df878078ac95f58fe8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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