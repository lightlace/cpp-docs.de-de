---
title: Ausnahmeverarbeitung | Microsoft-Dokumentation
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a2ded9c49a9f6935a5b268ccbefc4678af184029
ms.lasthandoff: 02/24/2017

---
# <a name="exception-processing"></a>Ausnahmeverarbeitung
Wenn ein Programm ausgeführt wird, kann eine Reihe von nicht ordnungsgemäße Bedingungen "und" Fehler "Ausnahmen" genannt auftreten. Hierzu gehören ungenügender Arbeitsspeicher aufgrund von Zuordnungsfehlern der Ressource sowie Fehler, um Dateien zu suchen.  
  
 Die Microsoft Foundation Class-Bibliothek verwendet eine Ausnahmebehandlung-Schema, das nach der von der ANSI-Standards Committee for C++ vorgeschlagenen eng modelliert wird. Ein Ausnahmehandler muss eingerichtet werden, vor dem Aufrufen einer Funktion, die eine nicht normale Situation auftreten kann. Wenn die Funktion eine nicht ordnungsgemäße Zustand auftritt, wird eine Ausnahme ausgelöst und Kontrolle wird an den Ausnahmehandler übergeben.  
  
 Ausnahmehandler werden mehrere Makros, die in der Microsoft Foundation Class-Bibliothek enthaltenen einrichten. Eine Reihe von anderen globalen Funktionen kann spezielle Ausnahmen auslösen, und Beenden von Programmen, bei Bedarf. Diese Makros und globale Funktionen fallen in die folgenden Kategorien:  
  
- Ausnahmemakros, die Struktur den Ausnahmehandler.  
  
- Exception-Throwing Funktionen), die Ausnahmen bestimmter Typen generieren.  
  
- Beenden-Funktionen, die Beendigung des Programms führen.  
  
 Beispiele und Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="exception-macros"></a>Ausnahmemakros  
  
|||  
|-|-|  
|[VERSUCHEN SIE ES](#try)|Kennzeichnet einen Codeblock für die ausnahmeverarbeitung.|  
|[CATCH](#catch)|Kennzeichnet einen Codeblock für Abfangen einer Ausnahme von der vorherigen **versuchen** Block.|  
|[CATCH_ALL](#catch_all)|Kennzeichnet einen Codeblock für das Abfangen aller Ausnahmen aus der vorherigen **versuchen** Block.|  
|[AND_CATCH](#and_catch)|Kennzeichnet einen Codeblock zum Abfangen von zusätzlichen Ausnahmetypen aus der vorherigen **versuchen** Block.|  
|[AND_CATCH_ALL](#and_catch_all)|Kennzeichnet einen Codeblock zum Abfangen von allen anderen zusätzliche Ausnahmetypen, die ausgelöst wird, in einem vorherigen **versuchen** Block.|  
|[END_CATCH](#end_catch)|Beendet die letzte **CATCH** oder `AND_CATCH` Codeblock.|  
|[END_CATCH_ALL](#end_catch_all)|Beendet den letzten `CATCH_ALL` Codeblock.|  
|[THROW](#throw)|Löst eine angegebene Ausnahme.|  
|[THROW_LAST](#throw_last)|Löst die gegenwärtig behandelte Ausnahme an den nächsten äußeren Handler.|  
  
### <a name="exception-throwing-functions"></a>Ausnahme auslösende Funktionen  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Löst eine Ausnahme Archiv.|  
|[AfxThrowFileException](#afxthrowfileexception)|Löst eine Ausnahme für die Datei.|  
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Löst eine Speicherausnahme.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Löst eine Ausnahme nicht unterstützt.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Löst eine Ausnahme für die Windows-Ressource nicht gefunden.|  
|[AfxThrowUserException](#afxthrowuserexception)|Löst eine Ausnahme in einer Anwendung Benutzer initiierten Aktion.|  
  
 MFC bietet zwei Ausnahme auslösende Funktionen speziell für OLE-Ausnahmen:  
  
### <a name="ole-exception-functions"></a>OLE-Ausnahme-Funktionen  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Löst eine Ausnahme innerhalb einer Funktion der OLE-Automatisierung.|  
|[AfxThrowOleException](#afxthrowoleexception)|Eine OLE-Ausnahme ausgelöst.|  
  
 Unterstützung von Datenbankausnahmen, die Datenbankklassen bieten zwei Ausnahmeklassen `CDBException` und `CDaoException`, und globale Funktionen zur Unterstützung der Ausnahme:  
  
### <a name="dao-exception-functions"></a>DAO-Funktionen  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Löst ein [CDaoException](../../mfc/reference/cdaoexception-class.md) aus Ihrem eigenen Code.|  
|[AfxThrowDBException](#afxthrowdbexception)|Löst ein [CDBException](../../mfc/reference/cdbexception-class.md) aus Ihrem eigenen Code.|  
  
 MFC bietet die folgenden Beendigungsfunktion:  
  
### <a name="termination-functions"></a>Terminierungsfunktion  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|Aufgerufen, tritt ein, um eine Anwendung, wenn ein schwerwiegender Fehler beendet.|  
  
##  <a name="a-nametrya--try"></a><a name="try"></a>VERSUCHEN SIE ES  
 Richtet eine **versuchen** Block.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>Hinweise  
 Ein **versuchen** Block identifiziert einen Codeblock, der Ausnahmen auslösen kann. Diese Ausnahmen werden im folgenden behandelt **CATCH** und `AND_CATCH` blockiert. Rekursion ist zulässig: Ausnahmen übergeben werden können, um eine äußere **versuchen** Block, entweder ignoriert oder mithilfe der `THROW_LAST` Makro. Ende der **versuchen** -block mit einer `END_CATCH` oder `END_CATCH_ALL` Makro.  
  
 Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CATCH](#catch).  

### <a name="requirements"></a>Anforderungen
Header: afx.h

##  <a name="a-namecatcha--catch"></a><a name="catch"></a>CATCH  
 Definiert einen Codeblock, der den ersten Ausnahmetyp in den vorherigen abfängt **versuchen** Block.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *exception_class*  
 Gibt den Ausnahmetyp zu testen. Eine Liste der standardmäßigen Ausnahmeklassen, finden Sie unter Klasse [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Gibt einen Namen für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt wird. Können den Zeigernamen auf das Ausnahmeobjekt innerhalb der **CATCH** Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Verarbeitung der Ausnahme-Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die Ursache der Ausnahme erhalten Abfragen. Aufrufen der `THROW_LAST` Makro, um die Verarbeitung in den nächsten äußeren Ausnahme Frame verschoben. Ende der **versuchen** -block mit einer `END_CATCH` Makro.  
  
 Wenn *Exception_class* ist die Klasse `CException`, und klicken Sie dann alle Arten der Ausnahme abgefangen werden. Sie können die [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) Member-Funktion, um zu bestimmen, welche spezifische Ausnahme ausgelöst wurde. Eine bessere Möglichkeit, mehrere Arten von Ausnahmen abzufangen ist die Verwendung sequenzielle `AND_CATCH` Anweisungen, die jeweils ein anderer Ausnahmetyp.  
  
 Durch das Makro wird die Ausnahme Objektzeiger erstellt. Sie müssen nicht selbst deklarieren.  
  
> [!NOTE]
>  Die **CATCH** als C++-Bereich durch die Klammern definiert ist. Wenn Sie in diesem Bereich Variablen deklarieren, sind sie nur innerhalb des Bereichs zugegriffen werden kann. Dies gilt auch für *Exception_object_pointer_name*.  
  
 Weitere Informationen zu Ausnahmen und die **CATCH** -Makro, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCExceptions&#26;](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="a-namecatchalla--catchall"></a><a name="catch_all"></a>CATCH_ALL  
 Definiert einen Codeblock, der alle Ausnahmetypen, die ausgelöst wird, in der vorherigen abfängt **versuchen** Block.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *exception_object_pointer_name*  
 Gibt einen Namen für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt wird. Können den Zeigernamen auf das Ausnahmeobjekt innerhalb der `CATCH_ALL` Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Verarbeitung der Ausnahme-Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die Ursache der Ausnahme erhalten Abfragen. Aufrufen der `THROW_LAST` Makro, um die Verarbeitung in den nächsten äußeren Ausnahme Frame verschoben. Bei Verwendung von `CATCH_ALL`, Ende der **versuchen** -block mit einer `END_CATCH_ALL` Makro.  
  
> [!NOTE]
>  Die `CATCH_ALL` als C++-Bereich durch die Klammern definiert ist. Wenn Sie in diesem Bereich Variablen deklarieren, sind sie nur innerhalb des Bereichs zugegriffen werden kann.  
  
 Weitere Informationen über Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  

##  <a name="a-nameandcatcha--andcatch"></a><a name="and_catch"></a>AND_CATCH  
 Definiert einen Codeblock zum Abfangen von zusätzliche Ausnahmetypen, die ausgelöst wird, in einem vorherigen **versuchen** Block.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *exception_class*  
 Gibt den Ausnahmetyp zu testen. Eine Liste der standardmäßigen Ausnahmeklassen, finden Sie unter Klasse [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Ein Name für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt wird. Können den Zeigernamen auf das Ausnahmeobjekt innerhalb der `AND_CATCH` Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der **CATCH** Makro mit einem Typ von Ausnahme abfangen und dann die `AND_CATCH` -Makros für jede nachfolgende abfängt. Ende der **versuchen** -block mit einer `END_CATCH` Makro.  
  
 Die Verarbeitung der Ausnahme-Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die Ursache der Ausnahme erhalten Abfragen. Rufen Sie die `THROW_LAST` Makro innerhalb der `AND_CATCH` UMSCHALT Verarbeitung an den nächsten äußeren Ausnahme Frame blockieren. `AND_CATCH`markiert das Ende der vorherigen **CATCH** oder `AND_CATCH` Block.  
  
> [!NOTE]
>  Die `AND_CATCH` als C++ Bereich (getrennt durch geschweifte Klammern) definiert ist. Wenn Sie in diesem Bereich Variablen deklarieren, denken Sie daran, dass sie nur innerhalb des Bereichs zugegriffen werden kann. Dies gilt auch für die *Exception_object_pointer_name* Variable.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CATCH](#catch).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
##  <a name="a-nameandcatchalla--andcatchall"></a><a name="and_catch_all"></a>AND_CATCH_ALL  
 Definiert einen Codeblock zum Abfangen von zusätzliche Ausnahmetypen, die ausgelöst wird, in einem vorherigen **versuchen** Block.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *exception_object_pointer_name*  
 Ein Name für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt wird. Können den Zeigernamen auf das Ausnahmeobjekt innerhalb der `AND_CATCH_ALL` Block. Diese Variable wird für Sie deklariert werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der **CATCH** Makro mit einem Typ von Ausnahme abfangen und dann die `AND_CATCH_ALL` Makro, um alle anderen nachfolgenden Typen abzufangen. Bei Verwendung von `AND_CATCH_ALL`, Ende der **versuchen** -block mit einer `END_CATCH_ALL` Makro.  
  
 Die Verarbeitung der Ausnahme-Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die Ursache der Ausnahme erhalten Abfragen. Rufen Sie die `THROW_LAST` Makro innerhalb der `AND_CATCH_ALL` UMSCHALT Verarbeitung an den nächsten äußeren Ausnahme Frame blockieren. `AND_CATCH_ALL`markiert das Ende der vorherigen **CATCH** oder `AND_CATCH_ALL` Block.  
  
> [!NOTE]
>  Die `AND_CATCH_ALL` als C++ Bereich (durch Klammern getrennt) definiert ist. Wenn Sie in diesem Bereich Variablen deklarieren, denken Sie daran, dass sie nur innerhalb des Bereichs zugegriffen werden kann.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameendcatcha--endcatch"></a><a name="end_catch"></a>END_CATCH  
 Markiert das Ende des letzten **CATCH** oder `AND_CATCH` Block.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den `END_CATCH` -Makro, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameendcatchalla--endcatchall"></a><a name="end_catch_all"></a>END_CATCH_ALL  
 Markiert das Ende des letzten `CATCH_ALL` oder `AND_CATCH_ALL` Block.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-namethrowa--throw-mfc"></a><a name="throw"></a>THROW (MFC)  
 Die angegebene Ausnahme.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>Parameter  
 *exception_object_pointer*  
 Verweist auf ein Exception-Objekt abgeleitet `CException`.  
  
### <a name="remarks"></a>Hinweise  
 **LÖST** Interrupts programmausführung, an die zugeordnete Steuerelement übergeben **CATCH** in Ihrem Programm blockieren. Wenn Sie nicht angegeben haben die **CATCH** zu blockieren, und dann das Steuerelement übergeben wird, um ein Microsoft Foundation Class Library-Modul, das einen Fehler Nachricht und wird beendet.  
  
 Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-namethrowlasta--throwlast"></a><a name="throw_last"></a>THROW_LAST  
 Löst die Ausnahme zurück an dem nächsten äußeren **CATCH** Block.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Makros können Sie eine lokale-Ausnahme aus. Wenn Sie versuchen, eine Ausnahme auslöst, die Sie soeben abgefangen haben, normalerweise Gültigkeitsbereich verlässt und gelöscht werden. Mit `THROW_LAST`, wird die Ausnahme ordnungsgemäß an die nächste übergeben **CATCH** Handler.  
  
 Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowarchiveexceptiona--afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 Löst eine Ausnahme Archiv.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>Parameter  
 `cause`  
 Gibt eine ganze Zahl, die den Grund für die Ausnahme angibt. Eine Liste der möglichen Werte finden Sie unter [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).  
  
 `lpszArchiveName`  
 Verweist auf eine Zeichenfolge mit dem Namen der `CArchive` -Objekt, das die Ausnahme verursacht hat, (falls verfügbar).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowfileexceptiona--afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileException  
 Löst eine Ausnahme für die Datei.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `cause`  
 Gibt eine ganze Zahl, die den Grund für die Ausnahme angibt. Eine Liste der möglichen Werte finden Sie unter [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).  
  
 `lOsError`  
 Enthält die Betriebssystem-Fehlernummer (falls verfügbar), der die Ursache der Ausnahme angibt. Finden Sie eine Liste der Fehlercodes Handbuch zu Ihrem Betriebssystem.  
  
 `lpszFileName`  
 Zeigt auf eine Zeichenfolge mit dem Namen der Datei, die die Ausnahme verursacht hat, (falls verfügbar).  
  
### <a name="remarks"></a>Hinweise  
 Sie sind verantwortlich für die Ursache ermitteln, basierend auf dem Betriebssystem-Fehlercode.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowmemoryexceptiona--afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 Löst eine Speicherausnahme.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, wenn Aufrufe an den zugrunde liegenden System-speicherzuordnungen (wie z. B. `malloc` und [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows-Funktion) fehl. Sie müssen nicht für Aufruf **neue** da **neue** löst eine Ausnahme Arbeitsspeichers automatisch, wenn die speicherbelegung fehlschlägt.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrownotsupportedexceptiona--afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 Löst eine Ausnahme, die das Ergebnis einer Anforderung für eine nicht unterstützte Funktion ist.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowresourceexceptiona--afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 Löst eine Ressourcenausnahme.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, wenn eine Windows-Ressource geladen werden kann.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowuserexceptiona--afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserException  
 Löst eine Ausnahme aus, um einen endbenutzervorgang zu beenden.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, unmittelbar nach dem `AfxMessageBox` wurde für den Benutzer ein Fehler gemeldet.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowoledispatchexceptiona--afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
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
 Der Fehlercode für die Anwendung.  
  
 `lpszDescription`  
 Verbale Beschreibung des Fehlers.  
  
 `nDescriptionID`  
 Ressourcen-ID für die verbale Beschreibung.  
  
 `nHelpID`  
 Ein Hilfekontext Hilfestellung bei der Anwendung (. HLP)-Datei.  
  
### <a name="remarks"></a>Hinweise  
 Die Informationen zu dieser Funktion kann durch die treibende Anwendung (Microsoft Visual Basic oder einer anderen Clientanwendung für OLE-Automatisierung) angezeigt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCExceptions&#25;](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxthrowoleexceptiona--afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleException  
 Erstellt ein Objekt vom Typ `COleException` und löst eine Ausnahme aus.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>Parameter  
 `sc`  
 Ein OLE-Statuscode, der den Grund für die Ausnahme angibt.  
  
 `hr`  
 Handle für ein Ergebniscode, der den Grund für die Ausnahme angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Version, die akzeptiert ein `HRESULT` als Argument in das entsprechende Ergebniscode konvertiert `SCODE`. Weitere Informationen zu `HRESULT` und `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameafxthrowdaoexceptiona--afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 Rufen Sie diese Funktion zum Auslösen einer Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) aus Ihrem eigenen Code.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>Parameter  
 `nAfxDaoError`  
 Ein Ganzzahlwert, der ein erweiterter Fehlercode DAO darstellt, die kann einer der Werte unter aufgeführt [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).  
  
 *SCODE*  
 Ein OLE-Fehlercode von DAO vom Typ `SCODE`. Weitere Informationen finden Sie unter [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft auch `AfxThrowDaoException`. In Ihrem Aufruf können Sie die Parameter oder beide übergeben. Z. B. wenn der auslösen soll die Fehler in definierten **CDaoException::nAfxDaoError** , aber Sie ist nicht wichtig die *Scode* -Parameter, übergeben Sie einen gültigen Code in der `nAfxDaoError` Parameter und akzeptieren Sie den Standardwert für *Scode*.  
  
 Informationen zu Ausnahmen, die im Zusammenhang mit den MFC-DAO-Klassen finden Sie unter Klasse `CDaoException` in diesem Handbuch und im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdb.h  
  
##  <a name="a-nameafxthrowdbexceptiona--afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException  
 Rufen Sie diese Funktion zum Auslösen einer Ausnahme vom Typ `CDBException` aus Ihrem eigenen Code.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 Ein Wert vom Typ **RETCODE**, definieren den Typ des Fehlers, der die Ausnahme verursacht hat.  
  
 `pdb`  
 Ein Zeiger auf die `CDatabase` -Objekt, das die datenquellenverbindung darstellt, der die Ausnahme zugeordnet ist.  
  
 `hstmt`  
 ODBC **Befehls beschäftigt** -Handle, das das Anweisungshandle gibt an, der die Ausnahme zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft `AfxThrowDBException` empfängt einen ODBC **RETCODE** von einem Aufruf von einer ODBC-API-Funktion und interpretiert die **RETCODE** eine außergewöhnliche Bedingung, sondern als eine vorhersehbare Fehler. Ein Fehler beim Lesen der Datenträger kann beispielsweise ein datenzugriffsvorgang führen.  
  
 Informationen zu den **RETCODE** ODBC definierten Werte finden Sie im Kapitel 8, "Das Abrufen von Informationen für Status und Fehler" der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Informationen über MFC-Erweiterungen für diese Codes finden Sie in der Klasse [CDBException](../../mfc/reference/cdbexception-class.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afx.h  
  
##  <a name="a-nameafxaborta--afxabort"></a><a name="afxabort"></a>AfxAbort  
 Die Standard-Beendigungsfunktion von MFC bereitgestellten.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>Hinweise  
 `AfxAbort`wird intern von MFC-Memberfunktionen aufgerufen werden, wenn es ist ein schwerwiegender Fehler, z. B. eine nicht abgefangene Ausnahme, die verarbeitet werden kann. Rufen Sie `AfxAbort` in dem seltenen Fall, wenn ein schwerwiegenden Fehler auftritt aus dem kann nicht wiederhergestellt werden.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CATCH](#catch).  

### <a name="requirements"></a>Anforderungen  
  **Header** afx.h   
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

