---
title: Pufferbearbeitung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5c9c6b61c03671da0bfe3b58456291ad642aa7ff
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="buffer-manipulation"></a>Pufferbearbeitung
Verwenden Sie diese Routinen, um auf Einzelbytebasis mit Arbeitsspeicherbereichen zu arbeiten.  
  
### <a name="buffer-manipulation-routines"></a>Routinen der Pufferbearbeitung  
  
|Routine|Verwendung|  
|-------------|---------|  
|[_memccpy](../c-runtime-library/reference/memccpy.md)|Kopiert Zeichen aus einem Puffer in einen anderen, bis das angegebene Zeichen oder die angegebene Anzahl von Zeichen kopiert wurde.|  
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|Gibt einen Zeiger auf das erste Vorkommen des angegebenen Zeichens innerhalb einer angegebenen Anzahl von Zeichen im Puffer zurück.|  
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|Vergleicht die angegebene Anzahl von Zeichen in zwei Puffern.|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Kopiert eine angegebene Anzahl von Zeichen aus einem Puffer in einen anderen.|  
|[_memicmp, _memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Vergleicht die angegebene Anzahl von Zeichen in zwei Puffern ohne Berücksichtigung der Groß- und Kleinschreibung.|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove_s, wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Kopiert eine angegebene Anzahl von Zeichen aus einem Puffer in einen anderen.|  
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Verwendet das angegebene Zeichen, um die angegebene Anzahl von Bytes im Puffer zu initialisieren.|  
|[_swab](../c-runtime-library/reference/swab.md)|Lagert Datenbytes aus und speichert sie am angegebenen Speicherort.|  
  
 Wenn die Quell- und Zielbereiche überlappen, garantiert nur `memmove`, dass die vollständige Quelle ordnungsgemäß kopiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
