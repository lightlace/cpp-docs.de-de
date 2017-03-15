---
title: "Verwendung von Stapeln | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Verwendung von Stapeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der gesamte Arbeitsspeicher jenseits der aktuellen Adresse von RSP wird als flüchtig angesehen: Das Betriebssystem oder ein Debugger können diesen Speicher während der Debugsitzung eines Benutzers oder eines Interrupthandlers überschreiben.  Daher muss RSP immer zuerst festgelegt werden, bevor Werte in einen Stapelrahmen geschrieben oder aus ihm gelesen werden können.  
  
 In diesem Abschnitt wird die Reservierung von Stapelspeicher für lokale Variablen und das systeminterne **alloca** erläutert.  
  
-   [Stapelreservierung](../build/stack-allocation.md)  
  
-   [Dynamische Parameterstapelbereichskonstruktion](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [Funktionstypen](../build/function-types.md)  
  
-   [malloc\-Ausrichtung](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## Siehe auch  
 [x64\-Softwarekonventionen](../build/x64-software-conventions.md)