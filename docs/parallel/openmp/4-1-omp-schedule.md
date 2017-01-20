---
title: "4.1 OMP_SCHEDULE"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 4.1 OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_SCHEDULE** gilt nur für **nach** und **für Ähnlichkeit**\-Direktiven, die den Typ des Zeitplans **Laufzeit**haben.  Der Typ der Zeitplan für all diese Segmentgröße und Schleifen können zur Laufzeit festgelegt werden, indem diese Umgebungsvariable auf einen der gültigen Zeitplan Typen festlegt und einem optionalen *chunk\_size*.  
  
 Für **nach** und **für Ähnlichkeit**\-Direktive, die nicht den Typ für einen Zeitplan **Laufzeit**haben, wird **OMP\_SCHEDULE** ignoriert.  Der Standardwert für diese Implementierung\-definiert Umgebungsvariable wird.  Wenn das optionale *chunk\_size* festgelegt ist, muss der Wert positiv sein.  Wenn nicht festgelegt ist, ein Wert von 1 angenommen werden, außer dass im Falle eines Zeitplans **static***chunk\_size* .  Für einen **static** Zeitplan wird die standardmäßige Segmentgröße leer iterations zu Schleife durch die Anzahl der Threads festgelegt, die der Schleife angewendet werden.  
  
 Beispiel:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## Querverweise:  
  
-   **nach**\-Direktive finden [2.4.1 Abschnitt](../../parallel/openmp/2-4-1-for-construct.md) auf Seite 11.  
  
-   **für Ähnlichkeit**\-Direktive finden [2.5.1 Abschnitt](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf Seite 16.