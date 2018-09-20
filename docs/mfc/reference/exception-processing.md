---
title: Ausnahmeverarbeitung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1711e634fca1b4350e8aca5f75f0de8a4b3a0e5f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417357"
---
# <a name="exception-processing"></a>Ausnahmeverarbeitung

Wenn ein Programm ausgeführt wird, kann eine Reihe von nicht ordnungsgemäßen Bedingungen und dem Namen "Ausnahmen" Fehler auftreten. Dazu können gehören, auf unzureichenden Arbeitsspeicher aufgrund von Zuordnungsfehlern der Ressource und Fehler, um Dateien zu suchen.

Die Microsoft Foundation Class-Bibliothek verwendet eine Ausnahmebehandlung-Schema, das genau eine vorgeschlagene vom ANSI-Standards Committee für C++ entwickelt wurde. Ein Ausnahmehandler muss eingerichtet werden, vor dem Aufrufen einer Funktion, die eine nicht normale Situation auftreten kann. Wenn die Funktion einen nicht ordnungsgemäßen Zustand auftritt, sie löst eine Ausnahme aus, und erhält die Kontrolle an den Ausnahmehandler.

Ausnahmehandler werden mehrere Makros, die in der Microsoft Foundation Class-Bibliothek enthaltenen einrichten. Eine Reihe von anderen globalen Funktionen kann spezielle Ausnahmen auslösen, und Beenden von Programmen, bei Bedarf. Diese Makros und globale Funktionen werden in der folgenden Kategorien fallen:

- Ausnahmemakros, die Struktur der Ausnahmehandler.

- Exception-Throwing Funktionen), das Generieren von Ausnahmen eines bestimmten Typs.

- Terminierungsfunktionen auf, die dazu führen, dass bei der Beendigung des Programms.

Beispiele und weitere Details finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="exception-macros"></a>Ausnahmemakros

|||
|-|-|
|[VERSUCHEN SIE ES](#try)|Kennzeichnet einen Codeblock für die ausnahmeverarbeitung an.|
|[CATCH](#catch)|Kennzeichnet einen Block von Code zum Abfangen einer Ausnahme aus vorhergehenden **versuchen** Block.|
|[CATCH_ALL](#catch_all)|Kennzeichnet einen Block von Code für das Abfangen aller Ausnahmen aus dem vorherigen **versuchen** Block.|
|[AND_CATCH](#and_catch)|Kennzeichnet einen Codeblock zum Abfangen von zusätzlichen Typen aus dem vorherigen **versuchen** Block.|
|[AND_CATCH_ALL](#and_catch_all)|Kennzeichnet einen Codeblock zum Abfangen von allen anderen zusätzlichen Ausnahmetypen, die ausgelöst wird, in einem vorhergehenden **versuchen** Block.|
|[END_CATCH](#end_catch)|Beendet die letzte **CATCH** oder **AND_CATCH** Codeblock.|
|[END_CATCH_ALL](#end_catch_all)|Beendet die letzte **CATCH_ALL** Codeblock.|
|[THROW](#throw)|Gibt eine angegebene Ausnahme.|
|[THROW_LAST](#throw_last)|Löst aus, die derzeit behandelten Ausnahme an den nächsten äußere Handler.|

### <a name="exception-throwing-functions"></a>Ausnahme auslösende Funktionen

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Löst eine Ausnahme Archiv.|
|[AfxThrowFileException](#afxthrowfileexception)|Löst eine Ausnahme für die Datei aus.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Löst eine Ausnahme für ungültiges Argument.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Gibt eine Arbeitsspeicher-Ausnahme.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Gibt eine nicht unterstützte Ausnahme.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Gibt eine Ausnahme für die Windows-Ressource nicht gefunden.|
|[AfxThrowUserException](#afxthrowuserexception)|Löst eine Ausnahme in einer Anwendung vom Benutzer initiierte Aktion aus.|

MFC bietet zwei Ausnahme auslösende Funktionen speziell für OLE-Ausnahmen:

### <a name="ole-exception-functions"></a>OLE-Ausnahme-Funktionen

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Löst eine Ausnahme in eine OLE-Automatisierung-Funktion.|
|[AfxThrowOleException](#afxthrowoleexception)|Eine OLE-Ausnahme ausgelöst.|

Um Datenbankausnahmen zu unterstützen, die Datenbankklassen stellen zwei Ausnahmeklassen `CDBException` und `CDaoException`, und globale Funktionen für die Unterstützung der Ausnahme:

### <a name="dao-exception-functions"></a>Funktionen für DAO-Ausnahme

|||
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|Löst eine [CDaoException](../../mfc/reference/cdaoexception-class.md) über Ihren eigenen Code.|
|[AfxThrowDBException](#afxthrowdbexception)|Löst eine [CDBException](../../mfc/reference/cdbexception-class.md) über Ihren eigenen Code.|

MFC bietet die folgenden Beendigungsfunktion:

### <a name="termination-functions"></a>Terminierungsfunktion

|||
|-|-|
|[AfxAbort](#afxabort)|Wird aufgerufen, tritt ein, um eine Anwendung, wenn ein schwerwiegender Fehler zu beenden.|

##  <a name="try"></a>  VERSUCHEN SIE ES

Richtet eine **versuchen** Block.

```
TRY
```

### <a name="remarks"></a>Hinweise

Ein **versuchen** Block identifiziert einen Codeblock, die möglicherweise Ausnahmen auslösen. Diese Ausnahmen werden behandelt, in der folgenden **CATCH** und **AND_CATCH** Blöcke. Rekursion ist zulässig: Ausnahmen können übergeben werden, um eine äußere **versuchen** entweder ignoriert oder mithilfe der THROW_LAST-Makro-Block. Ende der **versuchen** Block mit einer END_CATCH oder END_CATCH_ALL-Makro.

Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CATCH](#catch).

### <a name="requirements"></a>Anforderungen

Header: afx.h

##  <a name="catch"></a>  CATCH

Definiert einen Codeblock, der den ersten Ausnahmetyp, das Sie in der vorherigen abfängt **versuchen** Block.

```
CATCH(exception_class, exception_object_pointer_name)

```

### <a name="parameters"></a>Parameter

*exception_class*<br/>
Gibt den Typ der Ausnahme zu testen. Eine Liste der standard Ausnahmeklassen, finden Sie unter Klasse [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Gibt einen Namen für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt werden. Sie können den Zeigernamen auf das Ausnahmeobjekt in zugreifen der **CATCH** Block. Diese Variable wird für Sie deklariert werden.

### <a name="remarks"></a>Hinweise

Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Rufen Sie das THROW_LAST-Makro, um die Verarbeitung der nächste äußere Ausnahme Frame zu verschieben. Ende der **versuchen** Block mit einer END_CATCH-Makro.

Wenn *Exception_class* ist die Klasse `CException`, und klicken Sie dann allen Ausnahmetypen abgefangen werden. Sie können die [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) Member-Funktion, um zu bestimmen, welche spezifische Ausnahme ausgelöst wurde. Eine bessere Möglichkeit, verschiedene Arten von Ausnahmen abfangen ist die Verwendung sequenzielle **AND_CATCH** Anweisungen, die jeweils über einen anderen Ausnahmetyp.

Die Ausnahme Objektzeiger wird durch das Makro erstellt. Sie müssen sich nicht selbst deklarieren.

> [!NOTE]
>  Die **CATCH** Block wird definiert, wie eine C++-Bereich, der durch Klammern getrennt wird. Wenn Sie die Variablen in diesem Bereich deklarieren, sind sie nur innerhalb des Bereichs zugegriffen werden kann. Dies gilt auch für *Exception_object_pointer_name*.

Weitere Informationen zu Ausnahmen und der CATCH-Makro, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

##  <a name="catch_all"></a>  CATCH_ALL

Definiert einen Codeblock, der allen Ausnahmetypen, die ausgelöst wird, in der vorherigen abfängt **versuchen** Block.

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parameter

*exception_object_pointer_name*<br/>
Gibt einen Namen für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt werden. Sie können den Zeigernamen verwenden, das Ausnahmeobjekt in den Zugriff auf die `CATCH_ALL` Block. Diese Variable wird für Sie deklariert werden.

### <a name="remarks"></a>Hinweise

Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Rufen Sie die `THROW_LAST` Makro, um die Verarbeitung der nächste äußere Ausnahme Frame zu verschieben. Bei Verwendung von **CATCH_ALL**, Ende der **versuchen** Block mit einer END_CATCH_ALL-Makro.

> [!NOTE]
>  Die **CATCH_ALL** Block wird definiert, wie eine C++-Bereich, der durch Klammern getrennt wird. Wenn Sie die Variablen in diesem Bereich deklarieren, sind sie nur innerhalb des Bereichs zugegriffen werden kann.

Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="and_catch"></a>  AND_CATCH

Definiert einen Block von Code zum Abfangen von zusätzlichen Ausnahmetypen, die ausgelöst wird, in einem vorhergehenden **versuchen** Block.

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parameter

*exception_class*<br/>
Gibt den Typ der Ausnahme zu testen. Eine Liste der standard Ausnahmeklassen, finden Sie unter Klasse [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Ein Name für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt werden. Sie können den Zeigernamen verwenden, das Ausnahmeobjekt in den Zugriff auf die **AND_CATCH** Block. Diese Variable wird für Sie deklariert werden.

### <a name="remarks"></a>Hinweise

Verwenden Sie die CATCH-Makro, einem Ausnahmetyp abzufangen, und klicken Sie dann auf die AND_CATCH-Makro, um jedes nachfolgende Typs abzufangen. Ende der **versuchen** Block mit einer END_CATCH-Makro.

Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Rufen Sie die THROW_LAST-Makro in der **AND_CATCH** Verarbeitung an den nächsten äußeren Ausnahme Frame zu blockieren. **AND_CATCH** markiert das Ende der vorangehenden **CATCH** oder **AND_CATCH** Block.

> [!NOTE]
>  Die **AND_CATCH** Block wird definiert, wie eine C++-Bereich (getrennt durch geschweifte Klammern). Wenn Sie die Variablen in diesem Bereich deklarieren, denken Sie daran, dass sie nur innerhalb des Bereichs zugegriffen werden kann. Dies gilt auch für die *Exception_object_pointer_name* Variable.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CATCH](#catch).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h
##  <a name="and_catch_all"></a>  AND_CATCH_ALL

Definiert einen Block von Code zum Abfangen von zusätzlichen Ausnahmetypen, die ausgelöst wird, in einem vorhergehenden **versuchen** Block.

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parameter

*exception_object_pointer_name*<br/>
Ein Name für ein Ausnahmeobjekt Zeiger, der durch das Makro erstellt werden. Sie können den Zeigernamen verwenden, das Ausnahmeobjekt in den Zugriff auf die **AND_CATCH_ALL** Block. Diese Variable wird für Sie deklariert werden.

### <a name="remarks"></a>Hinweise

Verwenden der **CATCH** -Makro, um einen Ausnahmetyp abzufangen, und klicken Sie dann auf die AND_CATCH_ALL-Makro zum Abfangen von allen anderen nachfolgenden Typen. Bei Verwendung von AND_CATCH_ALL enden die **versuchen** Block mit einer END_CATCH_ALL-Makro.

Der ausnahmeverarbeitung Code können Sie das Ausnahmeobjekt, bei Bedarf, um weitere Informationen über die genaue Ursache der Ausnahme erhalten Abfragen. Rufen Sie die THROW_LAST-Makro in der **AND_CATCH_ALL** Verarbeitung an den nächsten äußeren Ausnahme Frame zu blockieren. **AND_CATCH_ALL** markiert das Ende der vorangehenden **CATCH** oder **AND_CATCH_ALL** Block.

> [!NOTE]
>  Die **AND_CATCH_ALL** Block wird definiert, wie eine C++-Bereich (der durch Klammern getrennt wird). Wenn Sie die Variablen in diesem Bereich deklarieren, denken Sie daran, dass sie nur innerhalb des Bereichs zugegriffen werden kann.

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="end_catch"></a>  END_CATCH

Markiert das Ende der letzten **CATCH** oder **AND_CATCH** Block.

```
END_CATCH
```

### <a name="remarks"></a>Hinweise

Weitere Informationen zu den END_CATCH-Makro, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="end_catch_all"></a>  END_CATCH_ALL

Markiert das Ende der letzten ** CATCH_ALL88 oder **AND_CATCH_ALL** Block.

```
END_CATCH_ALL
```

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="throw"></a>  THROW (MFC)

Wird die angegebene Ausnahme ausgelöst.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>Parameter

*exception_object_pointer*<br/>
Verweist auf ein Ausnahmeobjekt abgeleitet `CException`.

### <a name="remarks"></a>Hinweise

**LÖST** Ausführung, die Kontrolle an die zugeordnete des Programms **CATCH** in Ihrem Programm zu blockieren. Wenn Sie nicht angegeben haben die **CATCH** blockieren, und dann das Steuerelement übergeben wird, um ein Microsoft Foundation Class Library-Modul, das gibt einen Fehler-Nachricht und beendet wird.

Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="throw_last"></a>  THROW_LAST

Löst die Ausnahme zurück an dem nächsten äußeren **CATCH** Block.

```
THROW_LAST()
```

### <a name="remarks"></a>Hinweise

Dieses Makro können Sie eine lokal erstellte-Ausnahme auslösen. Wenn Sie versuchen, eine Ausnahme auszulösen, die Sie gerade erfasst haben, wird normalerweise verlassen den Gültigkeitsbereich und gelöscht werden. Mit **THROW_LAST**, wird die Ausnahme ordnungsgemäß auf die nächste übergeben **CATCH** Handler.

Weitere Informationen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrowarchiveexception"></a>  AfxThrowArchiveException

Löst eine Ausnahme Archiv.

```
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Parameter

*Ursache*<br/>
Gibt eine ganze Zahl, die den Grund für die Ausnahme angibt. Eine Liste der möglichen Werte finden Sie [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*lpszArchiveName*<br/>
Verweist auf eine Zeichenfolge, die mit dem Namen des der `CArchive` -Objekt, das die Ausnahme verursacht hat, (falls verfügbar).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrowfileexception"></a>  AfxThrowFileException

Löst eine Ausnahme für die Datei aus.

```
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parameter

*Ursache*<br/>
Gibt eine ganze Zahl, die den Grund für die Ausnahme angibt. Eine Liste der möglichen Werte finden Sie [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*lOsError*<br/>
Enthält die Betriebssystem-Fehlernummer, (falls verfügbar), der die Ursache der Ausnahme angibt. Finden Sie unter Ihrem Betriebssystem manuell eine Liste der Fehlercodes.

*lpszFileName*<br/>
Verweist auf eine Zeichenfolge, die mit dem Namen der Datei, die die Ausnahme verursacht hat, (falls verfügbar).

### <a name="remarks"></a>Hinweise

Sie sind verantwortlich für das Ermitteln der Ursache, die basierend auf dem Betriebssystem-Fehlercode.

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

## <a name="afxthrowinvalidargexception"></a>  AfxThrowInvalidArgException

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

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[CInvalidArgException-Klasse](cinvalidargexception-class.md)<br/>
[THROW](#throw)


##  <a name="afxthrowmemoryexception"></a>  AfxThrowMemoryException

Gibt eine Arbeitsspeicher-Ausnahme.

```
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Hinweise

Diese Funktion aufrufen, wenn Aufrufe an die zugrunde liegende System-speicherzuordnungen (z. B. **"malloc"** und [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows-Funktion) fehl. Sie müssen nicht für nenne **neue** da **neue** löst eine Speicherausnahme automatisch, wenn die speicherbelegung fehlschlägt.

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrownotsupportedexception"></a>  AfxThrowNotSupportedException

Löst eine Ausnahme, die das Ergebnis einer Anforderung für ein nicht unterstütztes Feature ist.

```
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrowresourceexception"></a>  AfxThrowResourceException

Löst eine Ressourcenausnahme aus.

```
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird normalerweise aufgerufen, wenn eine Windows-Ressource kann nicht geladen werden.

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrowuserexception"></a>  AfxThrowUserException

Löst eine Ausnahme aus, um einen endbenutzervorgang zu beenden.

```
void AfxThrowUserException();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird normalerweise aufgerufen, unmittelbar nach `AfxMessageBox` hat einen Fehler, die dem Benutzer gemeldet.

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrowoledispatchexception"></a>  AfxThrowOleDispatchException

Verwenden Sie diese Funktion eine Ausnahme in eine OLE-Automatisierung-Funktion.

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

*WCode*<br/>
Ein Fehlercode, die spezifisch für Ihre Anwendung.

*lpszDescription*<br/>
Mündliche Beschreibung des Fehlers.

*nDescriptionID*<br/>
Ressourcen-ID für die verbale fehlerbeschreibung.

*nHelpID*<br/>
Ein Hilfekontext Hilfe von Ihrer Anwendung (. HLP)-Datei.

### <a name="remarks"></a>Hinweise

Die Informationen zu dieser Funktion kann durch die treibende Anwendung (Microsoft Visual Basic oder eine andere OLE-Client-Anwendung) angezeigt werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxthrowoleexception"></a>  AfxThrowOleException

Erstellt ein Objekt des Typs `COleException` und löst eine Ausnahme aus.

```
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>Parameter

*SC*<br/>
Ein OLE-Statuscode, der die Ursache der Ausnahme angibt.

*HR*<br/>
Handle für ein Ergebniscode, der den Grund für die Ausnahme angibt.

### <a name="remarks"></a>Hinweise

Die Version, die ein HRESULT als Argument akzeptiert konvertiert, Ergebnis: in die entsprechende SCODE an. Weitere Informationen zu HRESULT und SCODE, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) im Windows SDK.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="afxthrowdaoexception"></a>  AfxThrowDaoException

Mit dieser Funktion wird zum Auslösen einer Ausnahme vom Typ [CDaoException](../../mfc/reference/cdaoexception-class.md) über Ihren eigenen Code.

```
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Parameter

*nAfxDaoError*<br/>
Ein ganzzahliger-Wert, der ein erweiterter Fehlercode DAO darstellt, die kann die Werte aufgeführt [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).

*scode*<br/>
Ein OLE-Fehlercode von DAO, des Typs SCODE. Weitere Informationen finden Sie unter [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).

### <a name="remarks"></a>Hinweise

Das Framework ruft auch `AfxThrowDaoException`. Aufruf können Sie einen der Parameter oder beide übergeben. Z. B. Wenn Sie eine der auslösen möchten die Fehler in definierten **CDaoException::nAfxDaoError** , aber Sie ist nicht wichtig die *Scode* Parameter, übergeben Sie einen gültigen Code in die *nAfxDaoError* Parameters und akzeptieren Sie den Standardwert für *Scode*.

Informationen zu Ausnahmen im Zusammenhang mit den MFC-DAO-Klassen finden Sie in der Klasse `CDaoException` in diesem Buch sowie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdb.h

##  <a name="afxthrowdbexception"></a>  AfxThrowDBException

Mit dieser Funktion wird zum Auslösen einer Ausnahme vom Typ `CDBException` über Ihren eigenen Code.

```
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Parameter

*nRetCode*<br/>
Ein Wert vom Typ "RETCODE", definieren den Typ des Fehlers, der die auszulösende Ausnahme verursacht hat.

*PDB-Datei*<br/>
Ein Zeiger auf die `CDatabase` Objekt, das die datenquellenverbindung darstellt, der die Ausnahme zugeordnet ist.

*Befehls beschäftigt*<br/>
Eine ODBC HSTMT-Handle, das das Anweisungshandle gibt an, das die Ausnahme zugeordnet ist.

### <a name="remarks"></a>Hinweise

Das Framework ruft `AfxThrowDBException` Wenn eine ODBC RETCODE von einem Aufruf von einer ODBC-API-Funktion empfängt und die "RETCODE" als eine außergewöhnliche Bedingung, die nicht als eine vorhersehbare Fehler interpretiert. Z. B. möglicherweise einen datenzugriffsvorgang. aufgrund der ein Fehler beim Lesen der Datenträger.

Informationen zu den "RETCODE"-Werten, die von ODBC definiert finden Sie im Kapitel 8: "Abrufen von Status und Informationen zu Fehlern" im Windows SDK. Informationen über MFC-Erweiterungen für diese Codes finden Sie in der Klasse [CDBException](../../mfc/reference/cdbexception-class.md).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

##  <a name="afxabort"></a>  AfxAbort

Die beenden-Standardfunktion, von MFC bereitgestellten.

```
void  AfxAbort();
```

### <a name="remarks"></a>Hinweise

`AfxAbort` wird intern von MFC-Memberfunktionen aufgerufen werden, wenn es ist ein schwerwiegender Fehler, z. B. eine nicht abgefangene Ausnahme, die nicht behandelt werden kann. Rufen Sie `AfxAbort` in dem seltenen Fall, wenn Sie einen schwerwiegenden Fehler auftritt, aus dem kann nicht wiederhergestellt werden.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CATCH](#catch).

### <a name="requirements"></a>Anforderungen

  **Header** afx.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)
