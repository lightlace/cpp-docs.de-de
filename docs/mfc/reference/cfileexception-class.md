---
title: CFileException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
ms.openlocfilehash: e6b1b25f9125701a212f379c925a80ff888d58f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485818"
---
# <a name="cfileexception-class"></a>CFileException-Klasse

Stellt eine dateibezogene Ausnahmebedingung dar.

## <a name="syntax"></a>Syntax

```
class CFileException : public CException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFileException::CFileException](#cfileexception)|Erstellt ein `CFileException`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFileException::ErrnoToException](#errnotoexception)|Gibt, dass Code, eine Laufzeit-Fehlernummer entspricht.|
|[CFileException::GetErrorMessage](#geterrormessage)|Ruft die Meldung mit einer Beschreibung der Ausnahme ab.|
|[CFileException::OsErrorToException](#oserrortoexception)|Einen Ursachencode für ein Betriebssystem-Fehlercode zurückgegeben.|
|[CFileException::ThrowErrno](#throwerrno)|Gibt eine Datei-Ausnahme, die basierend auf einer Common Language Runtime-Fehlernummer.|
|[CFileException::ThrowOsError](#throwoserror)|Gibt eine Datei-Ausnahme, die basierend auf einer Betriebssystem-Fehlernummer.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFileException::m_cause](#m_cause)|Enthält die portablen Code, der die Ursache der Ausnahme entspricht.|
|[CFileException::m_lOsError](#m_loserror)|Enthält die verwandten Betriebssystem-Fehlernummer.|
|[CFileException::m_strFileName](#m_strfilename)|Enthält den Namen der Datei für diese Ausnahme.|

## <a name="remarks"></a>Hinweise

Die `CFileException` Klasse enthält öffentliche Datenmember, die den Ursachencode für die portable und die Anzahl der Betriebssystem-System-spezifischer Fehler enthalten. Die Klasse bietet auch statische Memberfunktionen für das Auslösen von Ausnahmen der Datei und zum Zurückgeben von Fehlercodes der Ursache für Betriebssystem-Fehler und C-Laufzeitfehler.

`CFileException` Objekte werden erstellt und im ausgelöst `CFile` Memberfunktionen und in Memberfunktionen von abgeleiteten Klassen. Sie können auf zugreifen, diese Objekte innerhalb des Bereichs einer **CATCH** Ausdruck. Verwenden Sie zur Portabilität nur den Ursachencode, um den Grund für eine Ausnahme zu erhalten. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cfileexception"></a>  CFileException::CFileException

Erstellt eine `CFileException` -Objekt, das die Ursache und die Betriebssystem-Code in das Objekt speichert.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parameter

*Ursache*<br/>
Ein enumerierter Typ-Variable, die den Grund für die Ausnahme angibt. Finden Sie unter [CFileException::m_cause](#m_cause) eine Liste der möglichen Werte.

*lOsError*<br/>
Eine System-betriebssystemspezifische Ursache der Ausnahme, falls verfügbar. Die *lOsError* Parameter bietet mehr Informationen als *dazu führen, dass* ist.

*lpszArchiveName*<br/>
Verweist auf eine Zeichenfolge, die mit dem Namen des der `CFile` Objekt, die die Ausnahme verursacht.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowFileException](exception-processing.md#afxthrowfileexception).

> [!NOTE]
>  Die Variable *lOsError* gilt nur für `CFile` und `CStdioFile` Objekte. Die `CMemFile` -Klasse behandelt keine dieser Fehlercode.

##  <a name="errnotoexception"></a>  CFileException::ErrnoToException

Konvertiert den Wert des angegebenen Laufzeit-Bibliothekscode-Fehler in einem `CFileException` -Enumerationswert Fehler ab.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Parameter

*nErrno*<br/>
Ganzzahlige Fehlercode in der Laufzeit-Includedatei ERRNO definiert. H.

### <a name="return-value"></a>Rückgabewert

Ein Enumerationswert, der auf eine bestimmte Laufzeitbibliothek Fehlerwert entspricht.

### <a name="remarks"></a>Hinweise

Finden Sie unter [CFileException::m_cause](#m_cause) eine Liste der möglichen Enumerationswerten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

##  <a name="geterrormessage"></a>  CFileException::GetErrorMessage

Ruft ab, Text, der eine Ausnahme beschrieben wird.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Parameter

*lpszError*<br/>
[in, out] Zeiger auf einen Puffer, der eine Fehlermeldung empfängt.

*nMaxError*<br/>
[in] Die maximale Anzahl von Zeichen, die der angegebene Puffer gespeichert werden kann. Dies schließt das abschließende Nullzeichen.

*pnHelpContext*<br/>
[in, out] Zeiger auf eine Ganzzahl ohne Vorzeichen, die empfängt die Hilfekontext-ID. Wenn `NULL`, keine ID zurückgegeben.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn der angegebene Puffer zu klein ist, wird die Fehlermeldung abgeschnitten.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird `CFileException::GetErrorMessage`.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

##  <a name="m_cause"></a>  CFileException::m_cause

Enthält Werte, die von einem `CFileException`-Enumerationstyp definiert wurden.

```
int m_cause;
```

### <a name="remarks"></a>Hinweise

Dieses Datenelement ist eine öffentliche Variable des Typs **Int**. Die Enumeratoren und ihre Bedeutungen lauten wie folgt:

- `CFileException::none` 0: kein Fehler aufgetreten ist.

- `CFileException::genericException` 1: ein Unbekannter Fehler aufgetreten.

- `CFileException::fileNotFound` 2: die Datei konnte nicht gefunden werden.

- `CFileException::badPath` 3: alle oder einen Teil des Pfads ist ungültig.

- `CFileException::tooManyOpenFiles` 4: die zulässige Anzahl von geöffneten Dateien wurde überschritten.

- `CFileException::accessDenied` 5: die Datei konnte nicht zugegriffen werden.

- `CFileException::invalidFile` 6: Es wurde versucht, einen ungültigen Dateihandle zu verwenden.

- `CFileException::removeCurrentDir` 7: das aktuelle Arbeitsverzeichnis kann nicht entfernt werden.

- `CFileException::directoryFull` 8: Es sind keine weiteren Verzeichniseinträge.

- `CFileException::badSeek` 9: Fehler bei der Versuch, den Dateizeiger festzulegen.

- `CFileException::hardIO` 10: Es wurde ein Hardwarefehler.

- `CFileException::sharingViolation` 11: FREIGABE. EXE-Datei wurde nicht geladen werden, oder eine freigegebene Region wurde gesperrt.

- `CFileException::lockViolation` 12: Es wurde versucht, eine Region zu sperren, die bereits gesperrt wurde.

- `CFileException::diskFull` 14: der Datenträger voll ist.

- `CFileException::endOfFile` 15: das Dateiende wurde erreicht.

    > [!NOTE]
    >  Diese `CFileException`-Ursachenenumeratoren unterscheiden sich von den `CArchiveException`-Ursachenenumeratoren.

    > [!NOTE]
    > `CArchiveException::generic` ist veraltet. Verwenden Sie stattdessen `genericException`. Wenn **generische** in einer Anwendung verwendet und mit "/ CLR", und die resultierenden Syntaxfehler nicht leicht zu entschlüsseln, erstellt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

##  <a name="m_loserror"></a>  CFileException::m_lOsError

Enthält den Betriebssystem-Fehlercode für diese Ausnahme.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Hinweise

Finden Sie unter Ihrem Betriebssystem-Technisches Handbuch für die eine Liste der Fehlercodes. Dieses Datenelement ist eine öffentliche Variable vom Typ LONG aus.

##  <a name="m_strfilename"></a>  CFileException::m_strFileName

Enthält den Namen der Datei für diese Ausnahmebedingung.

```
CString m_strFileName;
```

##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException

Gibt einen Enumerator, der entspricht einem bestimmten *lOsError* Wert. Wenn der Fehlercode unbekannt ist, und klicken Sie dann die Funktion gibt `CFileException::generic`.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Parameter

*lOsError*<br/>
Ein Betriebssystem-System-spezifischen Fehlercode.

### <a name="return-value"></a>Rückgabewert

Ein Enumerationswert, der Wert eines bestimmten Betriebssystemfehlers entspricht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

##  <a name="throwerrno"></a>  CFileException::ThrowErrno

Erstellt eine `CFileException` Objekt entsprechend einer angegebenen *nErrno* Wert und dann wird die Ausnahme ausgelöst.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parameter

*nErrno*<br/>
Ganzzahlige Fehlercode in der Laufzeit-Includedatei ERRNO definiert. H.

*lpszFileName*<br/>
Ein Zeiger auf die Zeichenfolge, die mit dem Namen der Datei, die der Ausnahme verursacht hat, falls verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

##  <a name="throwoserror"></a>  CFileException::ThrowOsError

Löst eine `CFileException` entsprechend einer angegebenen *lOsError* Wert. Wenn der Fehlercode ist unbekannt, löst die Funktion eine Ausnahme, die als `CFileException::generic`.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parameter

*lOsError*<br/>
Ein Betriebssystem-System-spezifischen Fehlercode.

*lpszFileName*<br/>
Ein Zeiger auf die Zeichenfolge, die mit dem Namen der Datei, die der Ausnahme verursacht hat, falls verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>Siehe auch

[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)

