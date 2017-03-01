---
title: "Rückruffunktion für CDC:: setabortproc | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::SetAbortProc
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::SetAbortProc
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1ba16ea60d8b18abd1962ded2da7e11ff2ef09a1
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcsetabortproc"></a>Rückruffunktion für CDC::SetAbortProc
Der Name *AbortFunc* ist ein Platzhalter für den Namen der Anwendung bereitgestellte Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
#### <a name="parameters"></a>Parameter  
 *hPr*  
 Identifiziert den Gerätekontext.  
  
 `code`  
 Gibt an, ob ein Fehler aufgetreten ist. Es ist 0, wenn kein Fehler aufgetreten ist. Es ist **SP_OUTOFDISK** den Druck-Manager ist derzeit kein Speicherplatz mehr und mehr Speicherplatz verfügbar wird, wenn die Anwendung wartet. Wenn `code` ist **SP_OUTOFDISK**, die Anwendung muss nicht den Druckauftrag abzubrechen. Ist dies nicht der Fall ist, er muss liefern, den Druck-Manager durch Aufrufen der **PeekMessage** oder **GetMessage** Windows-Funktion.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert der Funktion Abort-Handler ist ungleich NULL, wenn der Druckauftrag ist, um den Vorgang fortzusetzen, und 0, wenn er abgebrochen wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Name muss exportiert werden, wie im Abschnitt Hinweise unter [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)


