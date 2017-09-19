---
title: SYSTEMTIME Structure1 | Microsoft-Dokumentation
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
- SYSTEMTIME structure
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 298b2673a3eb05525683f8269fcd415d5be1c80a
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="systemtime-structure1"></a>SYSTEMTIME-Structure1
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
 [!code-cpp[NVC_MFC_Utilities Nr.&39;](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime:: CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)


