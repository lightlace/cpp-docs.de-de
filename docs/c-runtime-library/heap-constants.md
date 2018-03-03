---
title: Heap-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2e1a15b371aa4f2997d453e2543123b279ac0df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="heap-constants"></a>Heap-Konstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <malloc.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Konstanten geben den Rückgabewert an, der den Heapstatus angibt.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_HEAPBADBEGIN`|Ursprüngliche Headerinformationen wurden nicht gefunden oder sind ungültig.|  
|`_HEAPBADNODE`|Ein ungültiger Knoten wurde gefunden, oder der Heap ist beschädigt.|  
|`_HEAPBADPTR`|**_pentry**-Feld der **_HEAPINFO**-Struktur enthält keinen gültigen Zeiger auf einen Heap (nur `_heapwalk`-Routine).|  
|`_HEAPEMPTY`|Der Heap wurde noch nicht initialisiert.|  
|`_HEAPEND`|Ende des Heaps wurde erfolgreich erreicht (nur `_heapwalk`-Routine).|  
|`_HEAPOK`|Heap ist konsistent (nur `_heapset`- und `_heapchk`-Routinen). Keine Fehler bisher; **_HEAPINFO**-Struktur enthält Informationen zum nächsten Eintrag (nur `_heapwalk`-Routine).|  
  
## <a name="see-also"></a>Siehe auch  
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)