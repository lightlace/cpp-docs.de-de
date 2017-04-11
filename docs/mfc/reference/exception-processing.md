---
title: Ausnahmeverarbeitung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros, exception handling
- DAO (Data Access Objects), exceptions
- OLE exceptions, MFC functions
- exceptions, processing
- exception macros
- termination functions, MFC
- MFC, exceptions
- exceptions, MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: fc136efaa6312edf3edfa8420411eda73e1c2468
ms.lasthandoff: 04/04/2017

---
# <a name="exception-processing"></a>Ausnahmeverarbeitung
Wenn ein Programm ausgeführt wird, kann eine Reihe von nicht ordnungsgemäße Bedingungen und namens "Ausnahmen" Fehler auftreten. Dazu können gehören, des Arbeitsspeichers, die aufgrund von Zuordnungsfehlern der Ressource sowie Fehler beim Suchen von Dateien zur Neige.  
  
 Die Microsoft Foundation Class-Bibliothek verwendet eine Ausnahmebehandlung-Schema, das eng nach der Komprimierung einer vorgeschlagen, durch die ANSI-Standards Committee für C++ modelliert wird. Ein Ausnahmehandler muss eingerichtet werden, vor dem Aufrufen einer Funktion, eine solche Situation auftreten kann. Wenn die Funktion eine nicht ordnungsgemäße Zustand auftritt, wird eine Ausnahme ausgelöst und Steuerelement wird an den Ausnahmehandler übergeben.  
  
 Ausnahmehandler werden mehrere Makros, die mit der Microsoft Foundation Class-Bibliothek enthalten einrichten. Eine Reihe von anderen globalen Funktionen kann spezielle Ausnahmen auslösen, und Beenden von Programmen, bei Bedarf. Diese Makros und globale Funktionen fallen in folgenden Kategorien:  
  
- Ausnahmemakros, die Struktur der Ausnahmehandler.  
  
- Exception-Throwing Funktionen), die Ausnahmen bestimmter Typen generieren.  
  
- Terminierungsfunktionen auf, die dazu führen, dass bei der Beendigung des Programms.  
  
 Beispiele und weitere Details finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="exception-macros"></a>Ausnahmemakros  
  
|||  
|-|-|  
|[VERSUCHEN SIE ES](#try)|Kennzeichnet einen Codeblock für die ausnahmeverarbeitung.|  
|[CATCH](#catch)|Kennzeichnet einen Codeblock für Abfangen einer Ausnahme aus der vorangehenden **versuchen** Block.|  
|[CATCH_ALL](#catch_all)|Kennzeichnet einen Codeblock für alle Ausnahmen von den vorherigen abfangen **versuchen** Block.|  
|[AND_CATCH](#and_catch)|Kennzeichnet einen Codeblock zum Abfangen von zusätzlichen Ausnahmetypen aus den vorherigen **versuchen** Block.|  
|[AND_CATCH_ALL](#and_catch_all)|Kennzeichnet einen Codeblock zum Abfangen von allen anderen zusätzliche Ausnahmetypen, die ausgelöst wird, in einem vorhergehenden **versuchen** Block.|  
|[END_CATCH](#end_catch)|Beendet die letzte **CATCH** oder `AND_CATCH` Codeblock.|  
|[END_CATCH_ALL](#end_catch_all)|Beendet die letzte `CATCH_ALL` Codeblock.|  
|[THROW](#throw)|Gibt eine angegebene Ausnahme.|  
|[THROW_LAST](#throw_last)|Löst aus, die derzeit behandelte Ausnahme an den nächsten äußeren Handler.|  
  
### <a name="exception-throwing-functions"></a>Ausnahme auslösende Funktionen  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Löst eine Ausnahme Archiv.|  
|[AfxThrowFileException](#afxthrowfileexception)|Löst eine Ausnahme der Datei aus.|  
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Löst eine Ausnahme für ungültiges Argument.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Gibt eine Arbeitsspeicher-Ausnahme.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Gibt eine nicht unterstützte Ausnahme.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Gibt eine Ausnahme für die Windows-Ressource nicht gefunden.|  
|[AfxThrowUserException](#afxthrowuserexception)|Löst eine Ausnahme in einer Anwendung Benutzer initiierten Aktion.|  
  
 MFC enthält zwei Ausnahme auslösende Funktionen speziell für OLE-Ausnahmen:  
  
### <a name="ole-exception-functions"></a>OLE-Ausnahme-Funktionen  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Löst eine Ausnahme innerhalb einer Funktion der OLE-Automatisierung.|  
|[AfxThrowOleException](#afxthrowoleexception)|Eine OLE-Ausnahme ausgelöst.|  
  
 Zur Unterstützung von Datenbankausnahmen Datenbankklassen bieten zwei Ausnahmeklassen, `CDBException` und `CDaoException`, und globale Funktionen unterstützen die Ausnahmetypen ermöglicht:  
  
### <a name="dao-exception-functions"></a>DAO-Funktionen  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Löst ein [CDaoException](../../mfc/reference/cdaoexception-class.md) aus Ihrem eigenen Code.|  
|[AfxThrowDBException](#afxthrowdbexception)|Löst ein [CDBException](../../mfc/reference/cdbexception-class.md) aus Ihrem eigenen Code.|  
  
 MFC bietet die folgenden Beendigungsfunktion:  
  
### <a name="termination-functions"></a>Terminierungsfunktion  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|Wird aufgerufen, tritt ein, um eine Anwendung, wenn ein schwerwiegender Fehler beendet.|  
  
##  <a name="try"></a>VERSUCHEN SIE ES  
 Richtet eine **versuchen** Block.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>Hinweise  
 Ein **versuchen** Block identifiziert einen Codeblock, der Ausnahmen auslösen kann. Diese Ausnahmen werden behandelt, in der folgenden **CATCH** und `AND_CATCH` blockiert. Rekursion ist zulässig: Ausnahmen übergeben werden können, um ein äußeres **versuchen** Block, ignorieren Sie diese oder mithilfe der `THROW_LAST` Makro. Ende der **versuchen** -block mit einer `END_CATCH` oder `END_CATCH_ALL` Makro.  
  
 Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CATCH](#catch).  

### <a name="requirements"></a>Anforderungen
Header: afx.h

##  <a name="catch"></a>CATCH  
 Definiert einen Codeblock, der den ersten Ausnahmetyp in den vorherigen abfängt **versuchen** Block.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *exception_class*  
 Gibt den Ausnahmetyp zu testen. Eine Liste der standardmäßigen Ausnahmeklassen, finden Sie in der Klasse [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Gibt einen Namen für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt werden soll. Können Sie den Zeigernamen auf das Ausnahmeobjekt innerhalb der **CATCH** Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, falls erforderlich, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Aufrufen der `THROW_LAST` Makro, um die Verarbeitung auf den nächsten äußeren Ausnahme Frame verschoben. Ende der **versuchen** -block mit einer `END_CATCH` Makro.  
  
 Wenn *Exception_class* ist die Klasse `CException`, und klicken Sie dann alle Ausnahmetypen abgefangen werden. Sie können die [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) Member-Funktion, um zu bestimmen, welche spezifische Ausnahme ausgelöst wurde. Eine bessere Möglichkeit, verschiedene Arten von Ausnahmen abfangen ist die Verwendung sequenzielle `AND_CATCH` Anweisungen, die jeweils über einen anderen Ausnahmetyp.  
  
 Die Ausnahme Objektzeiger wird durch das Makro erstellt. Sie müssen nicht selbst deklarieren.  
  
> [!NOTE]
>  Die **CATCH** Block als geschweifte Klammern getrennter C++ Bereich definiert wird. Wenn Sie in diesem Bereich Variablen deklarieren, sind sie nur innerhalb des Bereichs zugegriffen werden kann. Dies gilt auch für *Exception_object_pointer_name*.  
  
 Weitere Informationen zu Ausnahmen und die **CATCH** -Makro, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCExceptions #26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="catch_all"></a>CATCH_ALL  
 Definiert einen Codeblock, der alle Ausnahmetypen, die ausgelöst wird, in den vorherigen abfängt **versuchen** Block.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *exception_object_pointer_name*  
 Gibt einen Namen für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt werden soll. Können Sie den Zeigernamen auf das Ausnahmeobjekt innerhalb der `CATCH_ALL` Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, falls erforderlich, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Aufrufen der `THROW_LAST` Makro, um die Verarbeitung auf den nächsten äußeren Ausnahme Frame verschoben. Bei Verwendung von `CATCH_ALL`, Ende der **versuchen** -block mit einer `END_CATCH_ALL` Makro.  
  
> [!NOTE]
>  Die `CATCH_ALL` Block als geschweifte Klammern getrennter C++ Bereich definiert wird. Wenn Sie in diesem Bereich Variablen deklarieren, sind sie nur innerhalb des Bereichs zugegriffen werden kann.  
  
 Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  

##  <a name="and_catch"></a>AND_CATCH  
 Definiert einen Codeblock zum Abfangen von zusätzlichen Ausnahmetypen, die ausgelöst wird, in einem vorhergehenden **versuchen** Block.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *exception_class*  
 Gibt den Ausnahmetyp zu testen. Eine Liste der standardmäßigen Ausnahmeklassen, finden Sie in der Klasse [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Ein Name für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt wird. Können Sie den Zeigernamen auf das Ausnahmeobjekt innerhalb der `AND_CATCH` Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der **CATCH** Makro, das einen Typ von Ausnahme abfangen und dann die `AND_CATCH` Makro, um jede nachfolgende abfangen. Ende der **versuchen** -block mit einer `END_CATCH` Makro.  
  
 Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, falls erforderlich, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Rufen Sie die `THROW_LAST` Makro innerhalb der `AND_CATCH` UMSCHALT Verarbeitung an den nächsten äußeren Ausnahme Frame blockieren. `AND_CATCH`markiert das Ende der vorangehenden **CATCH** oder `AND_CATCH` Block.  
  
> [!NOTE]
>  Die `AND_CATCH` Block als ein C++-Bereich (geschweifte Klammern getrennter) definiert ist. Wenn Sie in diesem Bereich Variablen deklarieren, denken Sie daran, dass sie nur innerhalb des Bereichs zugegriffen werden kann. Dies gilt auch für die *Exception_object_pointer_name* Variable.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CATCH](#catch).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
##  <a name="and_catch_all"></a>AND_CATCH_ALL  
 Definiert einen Codeblock zum Abfangen von zusätzlichen Ausnahmetypen, die ausgelöst wird, in einem vorhergehenden **versuchen** Block.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *exception_object_pointer_name*  
 Ein Name für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt wird. Können Sie den Zeigernamen auf das Ausnahmeobjekt innerhalb der `AND_CATCH_ALL` Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der **CATCH** Makro, das einen Typ von Ausnahme abfangen und dann die `AND_CATCH_ALL` Makro, das alle anderen Typen nachfolgende abfangen. Bei Verwendung von `AND_CATCH_ALL`, Ende der **versuchen** -block mit einer `END_CATCH_ALL` Makro.  
  
 Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, falls erforderlich, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Rufen Sie die `THROW_LAST` Makro innerhalb der `AND_CATCH_ALL` UMSCHALT Verarbeitung an den nächsten äußeren Ausnahme Frame blockieren. `AND_CATCH_ALL`markiert das Ende der vorangehenden **CATCH** oder `AND_CATCH_ALL` Block.  
  
> [!NOTE]
>  Die `AND_CATCH_ALL` Block als ein C++-Bereich (geschweifte Klammern getrennter) definiert ist. Wenn Sie in diesem Bereich Variablen deklarieren, denken Sie daran, dass sie nur innerhalb des Bereichs zugegriffen werden kann.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="end_catch"></a>END_CATCH  
 Markiert das Ende der letzten **CATCH** oder `AND_CATCH` Block.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den `END_CATCH` -Makro, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="end_catch_all"></a>END_CATCH_ALL  
 Markiert das Ende der letzten `CATCH_ALL` oder `AND_CATCH_ALL` Block.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="throw"></a>THROW (MFC)  
 Wird die angegebene Ausnahme ausgelöst.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>Parameter  
 *exception_object_pointer*  
 Verweist auf ein Ausnahmeobjekt von abgeleiteten `CException`.  
  
### <a name="remarks"></a>Hinweise  
 **LÖST** Interrupts programmausführung, übergeben an die zugeordnete Steuerelement **CATCH** in Ihrem Programm blockieren. Wenn Sie nicht bereitgestellt haben die **CATCH** blockieren, und dann das Steuerelement übergeben wird, um ein Microsoft Foundation Class Library-Modul, das druckt einen Fehler-Nachricht und beendet wird.  
  
 Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="throw_last"></a>THROW_LAST  
 Löst die Ausnahme wieder an dem nächsten äußeren **CATCH** Block.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro können Sie eine lokal erstellte Ausnahme auslösen. Wenn Sie versuchen, eine Ausnahme auslöst, die Sie gerade erfasst haben, wird normalerweise verlassen den Gültigkeitsbereich und gelöscht werden. Mit `THROW_LAST`, wird die Ausnahme ordnungsgemäß an den nächsten übergeben **CATCH** Handler.  
  
 Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 Löst eine Ausnahme Archiv.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>Parameter  
 `cause`  
 Gibt eine ganze Zahl, die den Grund für die Ausnahme angibt. Eine Liste der möglichen Werte finden Sie [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).  
  
 `lpszArchiveName`  
 Verweist auf eine Zeichenfolge mit dem Namen des dem `CArchive` -Objekt, das die Ausnahme verursacht hat, (falls verfügbar).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrowfileexception"></a>AfxThrowFileException  
 Löst eine Ausnahme der Datei aus.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `cause`  
 Gibt eine ganze Zahl, die den Grund für die Ausnahme angibt. Eine Liste der möglichen Werte finden Sie [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).  
  
 `lOsError`  
 Enthält die Betriebssystem-Fehlernummer (falls verfügbar), die besagt, dass die Ursache der Ausnahme. Finden Sie unter Ihrem Betriebssystem manuell eine Liste der Fehlercodes.  
  
 `lpszFileName`  
 Verweist auf eine Zeichenfolge, die mit dem Namen der Datei, die die Ausnahme verursacht hat, (falls verfügbar).  
  
### <a name="remarks"></a>Hinweise  
 Sie sind verantwortlich für die Ursache anhand der Betriebssystem-Fehlercode ermitteln.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  

## <a name="afxthrowinvalidargexception"></a>AfxThrowInvalidArgException
Löst eine Ausnahme für ungültiges Argument.  
   
### <a name="syntax"></a>Syntax    
```
void AfxThrowInvalidArgException( );  
```  
   
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, wenn ungültige Argumente verwendet werden.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [CInvalidArgException-Klasse](cinvalidargexception-class.md)   
 [THROW](#throw)
  
  
##  <a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 Gibt eine Arbeitsspeicher-Ausnahme.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion werden, wenn Aufrufe an die zugrunde liegende System-speicherzuordnungen (z. B. `malloc` und [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows-Funktion) fehl. Sie müssen nicht für Aufrufen **neue** da **neue** löst eine Speicherausnahme automatisch, wenn die speicherbelegung fehlschlägt.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 Löst eine Ausnahme, die das Ergebnis einer Anforderung einer nicht unterstützten Funktion ist.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 Gibt eine Ressourcenausnahme.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, wenn eine Windows-Ressource kann nicht geladen werden.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrowuserexception"></a>AfxThrowUserException  
 Löst eine Ausnahme aus, um einen endbenutzervorgang zu beenden.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, unmittelbar nach `AfxMessageBox` wurde für den Benutzer ein Fehler gemeldet.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
 Verwenden Sie diese Funktion eine Ausnahme innerhalb einer Funktion der OLE-Automatisierung.  
  
```   
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,  
    LPCSTR lpszDescription,  
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,  
    UINT nDescriptionID,  
    UINT nHelpID = -1); 
```  
  
### <a name="parameters"></a>Parameter  
 `wCode`  
 Der Fehlercode für Ihre Anwendung spezifisch sind.  
  
 `lpszDescription`  
 Verbale Beschreibung des Fehlers.  
  
 `nDescriptionID`  
 Ressourcen-ID für die verbale fehlerbeschreibung.  
  
 `nHelpID`  
 Ein Hilfekontext für die Anwendung Help (. HLP)-Datei.  
  
### <a name="remarks"></a>Hinweise  
 Die Informationen zu dieser Funktion kann durch die steuernde Anwendung (Microsoft Visual Basic oder eine andere Clientanwendung für OLE-Automatisierung) angezeigt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCExceptions #25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxthrowoleexception"></a>AfxThrowOleException  
 Erstellt ein Objekt des Typs `COleException` und löst eine Ausnahme aus.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>Parameter  
 `sc`  
 Ein OLE-Statuscode, der die Ursache der Ausnahme angibt.  
  
 `hr`  
 Handle für einen Ergebniscode, der die Ursache der Ausnahme angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Version, die akzeptiert ein `HRESULT` als ein Argument dieses Resultat den Code in die entsprechende konvertiert `SCODE`. Weitere Informationen zu `HRESULT` und `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 Mit dieser Funktion wird zum Auslösen einer Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) aus Ihrem eigenen Code.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>Parameter  
 `nAfxDaoError`  
 Ein Ganzzahlwert, ein DAO erweiterter Fehlercode darstellt, dem kann einen der Werte unter aufgeführt werden [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).  
  
 *SCODE*  
 Ein OLE-Fehlercode aus DAO vom Typ `SCODE`. Informationen finden Sie unter [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft auch `AfxThrowDaoException`. Aufrufen können Sie einen der Parameter oder beides übergeben. Z. B. eines auslösen sollen die Fehler in definierten **CDaoException::nAfxDaoError** , aber Sie ist nicht wichtig die *Scode* Parameter, übergeben Sie einen gültigen Code in der `nAfxDaoError` Parameter, und akzeptieren Sie den Standardwert für *Scode*.  
  
 Informationen zu Ausnahmen, die im Zusammenhang mit den MFC-DAO-Klassen finden Sie in der Klasse `CDaoException` in diesem Handbuch und im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdb.h  
  
##  <a name="afxthrowdbexception"></a>AfxThrowDBException  
 Mit dieser Funktion wird zum Auslösen einer Ausnahme vom Typ `CDBException` aus Ihrem eigenen Code.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 Ein Wert vom Typ **RETCODE**, definieren den Typ des Fehlers, der die Ausnahme ausgelöst wird, verursacht hat.  
  
 `pdb`  
 Ein Zeiger auf die `CDatabase` Objekt, das die datenquellenverbindung darstellt, der die Ausnahme zugeordnet ist.  
  
 `hstmt`  
 Ein ODBC **Befehls beschäftigt** -Handle, das das Anweisungshandle gibt an, der die Ausnahme zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft `AfxThrowDBException` ODBC empfängt **RETCODE** von einem Aufruf einer ODBC-API-Funktion und interpretiert die **RETCODE** als eine Ausnahmebedingung statt vorhersehbare Fehler. Beispielsweise kann eine Daten Zugriff aufgrund eines Datenträgers Lesefehler fehlschlagen.  
  
 Informationen zu den **RETCODE** Werte definiert, die von ODBC, finden Sie in Kapitel 8, "Abrufen von Informationen für Status und Fehler" in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Informationen über MFC-Erweiterungen für diese Codes finden Sie in der Klasse [CDBException](../../mfc/reference/cdbexception-class.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="afxabort"></a>AfxAbort  
 Der Standard-Beendigungsfunktion von MFC bereitgestellten.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>Hinweise  
 `AfxAbort`wird intern von MFC-Memberfunktionen aufgerufen werden, wenn es ist ein schwerwiegender Fehler, z. B. eine nicht abgefangene Ausnahme, die nicht behandelt werden kann. Sie können Aufrufen `AfxAbort` in dem seltenen Fall, wenn Sie einen schwerwiegenden Fehler auftreten, aus dem kann nicht wiederhergestellt werden.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CATCH](#catch).  

### <a name="requirements"></a>Anforderungen  
  **Header** afx.h   
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

