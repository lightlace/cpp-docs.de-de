---
title: Steht in Konflikt mit der X86 Compiler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b2b9c4cf871e8436a8da34a862d205541e7dc5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="conflicts-with-the-x86-compiler"></a>Konflikt mit dem x86-Compiler
Datentypen, die größer als 4 Bytes auf dem Stapel nicht automatisch ausgerichtet sind, bei der Verwendung der X86 Compiler zum Kompilieren einer Anwendung. Da die Architektur für die X86 Compiler kann ein ausgerichteten 4-Byte-Stapel, etwas größer als 4 Bytes, z. B. eine 64-Bit-Ganzzahl, kann nicht automatisch in eine 8-Byte-Adresse ausgerichtet sein.  
  
 Arbeiten mit nicht ausgerichteten Daten hat zwei Auswirkungen.  
  
-   Es kann nicht ausgerichtete Speicherorte zuzugreifen, als auf ausgerichtete dauert länger dauern.  
  
-   Nicht ausgerichtete Speicherorte können nicht in interlocked-Vorgänge verwendet werden.  
  
 Wenn Sie eine strengere Ausrichtung benötigen, verwenden Sie `__declspec(align(N)) on your variable declarations`. Dies bewirkt, dass den Compiler den Stapel, um die Parameterspezifikation dynamisch ausrichten. Anpassen der Stapel dynamisch zur Laufzeit kann jedoch langsamer Ausführung der Anwendung führen.  
  
## <a name="see-also"></a>Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)   
 [align](../cpp/align-cpp.md)