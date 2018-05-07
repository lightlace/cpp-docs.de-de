---
title: SYSTEMTIME Structure1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97a0042adaa223fc5898c057f191f7b750fa230f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

