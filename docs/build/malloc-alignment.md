---
title: "malloc-Ausrichtung | Microsoft Docs"
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
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# malloc-Ausrichtung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[malloc](../c-runtime-library/reference/malloc.md) gibt immer den Speicher zurück, der zum Speichern eines beliebigen Objekts geeignet ist, das eine grundlegende Ausrichtung hat und in den zugeordneten Speicher passt.  Eine *grundlegende Ausrichtung* ist eine Ausrichtung, die kleiner oder gleich der größten Ausrichtung ist, die von der Implementierung ohne Ausrichtungsspezifikation unterstützt wird. \(In Visual C\+\+ ist dies die Ausrichtung, die für einen `double` oder 8 Bytes erforderlich ist.  In einem Code, der auf 64\-Bit\-Plattformen ausgerichtet ist, sind es 16 Bytes.\) Beispielsweise kann eine Vier\-Byte\-Speicherbelegung an einer Begrenzung ausgerichtet werden, die ein Objekt unterstützt, das maximal vier Byte groß ist.  
  
 Visual C\+\+ unterstützt Typen mit einer *erweiterten Ausrichtung*, die auch als *über\-ausgerichtete* Typen bezeichnet werden.  Die SEE\-Typen [\_\_m128](../cpp/m128.md) und `__m256` sowie die Typen, die von `__declspec(align(``n``))` deklariert werden, wobei `n` größer ist als 8, verfügen beispielsweise über eine erweiterte Ausrichtung.  Eine Speicherausrichtung an einer Grenze, die für ein Objekt geeignet ist, das eine erweiterte Ausrichtung erfordert, wird von `malloc` nicht gewährleistet.  Verwenden Sie zur Speicherbelegung für über\-ausgerichtete Typen [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) und verwandte Funktionen.  
  
## Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)   
 [align](../cpp/align-cpp.md)   
 [\_\_declspec](../cpp/declspec.md)