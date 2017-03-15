---
title: Klasse CSimpleException | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException class
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5612d76a2351b9898b8ffe082844686d21fcd7a0
ms.lasthandoff: 02/24/2017

---
# <a name="csimpleexception-class"></a>CSimpleException-Klasse
Diese Klasse ist eine Basisklasse für ressourcenkritische MFC-Ausnahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Stellt Text zu einem Fehler, der aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CSimpleException`ist die Basisklasse für ressourcenkritische MFC-Ausnahmen und übernimmt den Besitz und die Initialisierung einer Fehlermeldung. Die folgenden Klassen verwenden `CSimpleException` als Basisklasse:  
  
|||  
|-|-|  
|[CMemoryException-Klasse](../../mfc/reference/cmemoryexception-class.md)|Out-of-Memory-Ausnahme|  
|[CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)|Anforderungen für ein nicht unterstützter Vorgang|  
|[CResourceException-Klasse](../../mfc/reference/cresourceexception-class.md)|Windows-Ressource wurde nicht gefunden oder nicht erstellt|  
|[CUserException-Klasse](../../mfc/reference/cuserexception-class.md)|Ausnahme, die eine Ressource angibt konnte nicht gefunden werden|  
|[CInvalidArgException-Klasse](../../mfc/reference/cinvalidargexception-class.md)|Ausnahme, die ein ungültiges Argument angibt.|  
  
 Da `CSimpleException` ist eine abstrakte Basisklasse, die nicht deklariert einen `CSimpleException` direkt. Stattdessen müssen Sie abgeleitete Objekte, z. B. die in der vorherigen Tabelle deklarieren. Wenn Sie eine eigene abgeleitete Klasse deklarieren, verwenden Sie die vorherigen Klassen als Modell.  
  
 Weitere Informationen finden Sie unter der [CException-Klasse](../../mfc/reference/cexception-class.md) Thema und [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="a-namecsimpleexceptiona--csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a>CSimpleException::CSimpleException  
 Der Konstruktor.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutoDelete`  
 Geben Sie **TRUE** Wenn der Speicher für die `CSimpleException` Objekt auf dem Heap zugeordnet wurde. Dies bewirkt, dass die `CSimpleException` -Objekt, bei dem gelöscht werden die **löschen** Member-Funktion wird aufgerufen, um die Ausnahme zu löschen. Geben Sie **FALSE** Wenn das `CSimpleException` Objekt ist auf dem Stapel oder ein globales Objekt. In diesem Fall die `CSimpleException` Objekt werden nicht gelöscht, wenn die **löschen** -Memberfunktion aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen normalerweise nicht direkt aufrufen dieses Konstruktors. Eine Funktion, die eine Ausnahme auslöst, sollte eine Instanz von Erstellen einer `CException`-abgeleitete Klasse, und rufen Sie dessen Konstruktor verwenden, oder es auslösen soll, verwenden Sie eine der MFC-Funktionen, wie z. B. [AfxThrowFileException](exception-processing.md#afxthrowfileexception), um einen vordefinierten Typ auslösen.  
  
##  <a name="a-namegeterrormessagea--csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
 Rufen Sie diese Memberfunktion, um Text zu einem Fehler bereitstellen, der aufgetreten ist.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszError`  
 Ein Zeiger auf einen Puffer, der eine Fehlermeldung angezeigt wird.  
  
 `nMaxError`  
 Die maximale Anzahl von Zeichen, die der Puffer aufnehmen kann, einschließlich der **NULL** Abschlusszeichen.  
  
 `pnHelpContext`  
 Die Adresse einer **UINT** erhalten, die Hilfe-Kontext-ID Wenn **NULL**, keine ID zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; Andernfalls wird 0 Wenn keine Fehlermeldungstext verfügbar.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Ausnahmebehandlung](../../mfc/exception-handling-in-mfc.md)




