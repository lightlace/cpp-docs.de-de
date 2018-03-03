---
title: SYSTEMTIME Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07af222a3d51ff1cc71076d5bbcc3513a3d6cad4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
Die Struktur `SYSTEMTIME` stellt ein Datum und eine Uhrzeit dar, mit jeweils einzelnen Membern für Monat, Tag, Jahr, Wochentag, Stunde, Minute, Sekunde und Millisekunde.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _SYSTEMTIME {  
    WORD wYear;  
    WORD wMonth;  
    WORD wDayOfWeek;  
    WORD wDay;  
    WORD wHour;  
    WORD wMinute;  
    WORD wSecond;  
    WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### <a name="parameters"></a>Parameter  
 *Mitglieder "wYear"*  
 Das aktuelle Jahr.  
  
 *"wMonth"*  
 Der aktuelle Monat; Januar ist 1.  
  
 *wDayOfWeek*  
 Der aktuelle Wochentag; Sonntag ist 0, Montag ist 1, usw.  
  
 *"wDay"*  
 Der aktuelle Tag des Monats.  
  
 *wHour*  
 Die aktuelle Stunde.  
  
 *"wMinute"*  
 Die aktuelle Minute.  
  
 *wSecond*  
 Der aktuelle Sekunde.  
  
 *wMilliseconds*  
 Die aktuelle Millisekunde.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime:: CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

