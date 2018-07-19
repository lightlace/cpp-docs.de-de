---
title: MINMAXINFO-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf9a6e6a1397b9361df5372af09be8e61d997e62
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337813"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO-Struktur
Die `MINMAXINFO` Struktur enthält Informationen über die Größe eines Fensters maximiert und die Position und die nachverfolgung von minimalen und maximalen Größe.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagMINMAXINFO {  
    POINT ptReserved;  
    POINT ptMaxSize;  
    POINT ptMaxPosition;  
    POINT ptMinTrackSize;  
    POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### <a name="parameters"></a>Parameter  
 *ptReserved*  
 Für die interne Verwendung vorgesehen.  
  
 *ptMaxSize*  
 Gibt an, die maximierten Breite (point.x) und der maximierten Höhe (point.y) des Fensters.  
  
 *ptMaxPosition*  
 Gibt die Position des linken Rands des maximierten Fensters (point.x) und die Position des oberen Rands der maximierten Fensters (point.y).  
  
 *ptMinTrackSize*  
 Gibt die minimale Trackingbreite (point.x) und die minimale Höhe (point.y) des Fensters nachverfolgen.  
  
 *ptMaxTrackSize*  
 Gibt die maximale Breite (point.x) nachverfolgen und die maximale Höhe (point.y) des Fensters nachverfolgen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

