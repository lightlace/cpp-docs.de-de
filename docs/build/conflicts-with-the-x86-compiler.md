---
title: Steht in Konflikt mit der X86 Compiler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd72de4922c297b4a230e0dc0fb606b56a2a473
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366912"
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