---
title: FILETIME-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FILETIME
dev_langs: C++
helpviewer_keywords: FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ecb4814a8bfc0b94bce8e160b973a81bb54cd48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="filetime-structure"></a>FILETIME-Struktur
Die `FILETIME` Struktur ist ein 64-Bit-Wert, der die Anzahl der 100-Nanosekunden-Intervalle seit dem 1. Januar 1601 darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _FILETIME {  
    DWORD dwLowDateTime;   /* low 32 bits */  
    DWORD dwHighDateTime;  /* high 32 bits */  
} FILETIME, *PFILETIME, *LPFILETIME;  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwLowDateTime*  
 Gibt den niedrigen 32 Bits der Dateizeit an.  
  
 *dwHighDateTime*  
 Gibt die hohen 32 Bits der Dateizeit an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** windef.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime:: CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

