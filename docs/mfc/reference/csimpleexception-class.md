---
title: CSimpleException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d04a2f643add489d3302e58a9bde995303ecddd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369924"
---
# <a name="csimpleexception-class"></a>CSimpleException-Klasse
Diese Klasse ist eine Basisklasse für ressourcenkritische MFC-Ausnahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Stellt Text zu einem Fehler, der aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CSimpleException` ist die Basisklasse für ressourcenkritische MFC-Ausnahmen und übernimmt den Besitz und die Initialisierung einer Fehlermeldung. Folgende Klassen geben mit `CSimpleException` als Basisklasse:  
  
|||  
|-|-|  
|[CMemoryException-Klasse](../../mfc/reference/cmemoryexception-class.md)|Out-of-Memory-Ausnahme|  
|[CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)|Anforderungen für einen nicht unterstützten Vorgang|  
|[CResourceException-Klasse](../../mfc/reference/cresourceexception-class.md)|Windows-Ressource wurde nicht gefunden oder nicht erstellt werden|  
|[CUserException-Klasse](../../mfc/reference/cuserexception-class.md)|Ausnahme, die eine Ressource konnte nicht gefunden werden|  
|[CInvalidArgException-Klasse](../../mfc/reference/cinvalidargexception-class.md)|Ausnahme, die ein ungültiges Argument angibt.|  
  
 Da `CSimpleException` ist eine abstrakte Basisklasse, können Sie nicht deklarieren einer `CSimpleException` -Objekts direkt. Stattdessen müssen Sie abgeleitete Objekte, z. B. die in der vorherigen Tabelle deklarieren. Wenn Sie eine eigene abgeleitete Klasse deklarieren, verwenden Sie die vorherigen Klassen als Modell.  
  
 Weitere Informationen finden Sie unter der [CException-Klasse](../../mfc/reference/cexception-class.md) Thema und [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException  
 Der Konstruktor.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutoDelete`  
 Geben Sie **"true"** Wenn der Arbeitsspeicher für die `CSimpleException` Objekt auf dem Heap zugewiesen wurde. Dies bewirkt, dass die `CSimpleException` zu Wenn löschendes Objekt die **löschen** Member-Funktion wird aufgerufen, um die Ausnahme zu löschen. Geben Sie **"false"** Wenn die `CSimpleException` Objekt ist auf dem Stapel oder ein globales Objekt. In diesem Fall die `CSimpleException` Objekt werden nicht gelöscht, sobald die **löschen** Memberfunktion aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen normalerweise nicht direkt aufrufen dieses Konstruktors. Erstellen Sie eine Funktion, die eine Ausnahme auslöst, sollte eine Instanz von einem `CException`-abgeleitete Klasse, und rufen Sie ihren Konstruktor, oder es sollten gehen die MFC-Bibliothek auslösen, Funktionen, wie z. B. [AfxThrowFileException](exception-processing.md#afxthrowfileexception), einen vordefinierten Typ ausgelöst werden soll.  
  
##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage  
 Rufen Sie diese Memberfunktion zum Bereitstellen von Text zu einem Fehler, der aufgetreten ist.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszError`  
 Ein Zeiger auf einen Puffer, der folgende Fehlermeldung angezeigt wird.  
  
 `nMaxError`  
 Die maximale Anzahl von Zeichen, die der Puffer aufnehmen kann, einschließlich der **NULL** Abschlusszeichen.  
  
 `pnHelpContext`  
 Die Adresse von einem **"uint"** erhalten, die die Hilfe-Kontext-ID Wenn **NULL**, keine ID zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; Andernfalls wird 0, wenn kein Text der Fehlermeldung zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Ausnahmebehandlung](../../mfc/exception-handling-in-mfc.md)



