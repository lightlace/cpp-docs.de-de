---
title: -HEAP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /heap
dev_langs:
- C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5306df647801d7d1467aa0f44bfacca18fccaff3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372216"
---
# <a name="heap"></a>/HEAP
Legt die Größe des Heap in Bytes fest. Diese Option gilt nur für ausführbare Dateien.  
  
```  
  
/HEAP:  
reserve[,commit]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `reserve` Argument gibt die gesamte ursprüngliche Heapreservierung im virtuellen Speicher an. Standardmäßig beträgt die Größe des Heaps 1 MB. [EDITBIN-Referenz](../../build/reference/editbin-reference.md) rundet den angegebenen Wert in das nächste Vielfache von 4 Bytes.  
  
 Das optionale `commit` -Argument vom Betriebssystem interpretiert wird. Auf einem Windows-Betriebssystem gibt es die wie viel physischen Arbeitsspeicher zum Zuordnen und der Menge der zusätzlichen Arbeitsspeicher reserviert werden, wenn der Heap erweitert werden muss. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Eine höhere `commit` Wert lässt das System weniger belegt werden häufig auf, wenn die app mehr Heapspeicher benötigt, erhöht aber die arbeitsspeicheranforderungen und möglicherweise die app-Start-Dauer. Die `commit` Wert muss kleiner als oder gleich der `reserve` Wert.  
  
 Geben Sie die `reserve` und `commit` Werten in Decimal oder C-Sprache oktale oder hexadezimale Schreibweise. Beispielsweise kann ein Wert von 1 MB als 1048576 Dezimal, oder als 0 x 100000 im hexadezimalen Format oder als 04000000 in oktalen angegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)