---
title: MINMAXINFO-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MINMAXINFO
dev_langs: C++
helpviewer_keywords: MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 997e00d8d4fd70281f2dbfeeecbc9d5823c5050a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO-Struktur
Die `MINMAXINFO` Struktur enthält Informationen über ein Fenster maximiert Größe und Position und die minimalen und maximalen Tracking-Größe.  
  
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
 Gibt die maximierten Breite (point.x) und der maximierten Höhe (point.y) des Fensters.  
  
 `ptMaxPosition`  
 Gibt die Position des linken Rands des maximierten Fensters (point.x) und die Position des oberen Rands des maximierten Fensters (point.y).  
  
 *ptMinTrackSize*  
 Gibt die minimale Trackingbreite (point.x) und die minimale Höhe (point.y) des Fensters nachverfolgen.  
  
 *ptMaxTrackSize*  
 Gibt die maximale Breite (point.x) nachverfolgen und die maximale Höhe (point.y) des Fensters nachverfolgen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

