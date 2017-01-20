---
title: "VarArgs"
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
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# VarArgs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Parameter über VarArgs übergeben werden \(z. B. Argumente mit Ellipsen\), wird im Wesentlichen die normale Parameterübergabe angewendet, einschließlich dem Zwischenspeichern des fünften und der nachfolgenden Argumente.  Durch die aufgerufene Funktion wird auch in diesem Fall sichergestellt, dass Argumente gespeichert werden, deren Adressen akzeptiert wurden.  Nur Gleitkommawerte sind sowohl im Ganzzahl\- als auch im Gleitkommaregister enthalten, wenn von der aufgerufenen Funktion der Wert in den Ganzzahlregistern erwartet wird.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)