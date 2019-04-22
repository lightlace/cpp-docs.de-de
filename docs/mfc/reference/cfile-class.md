---
title: CFile-Klasse
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: db499ffa5f1d82b6e3622287f86132930a929102
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768550"
---
# <a name="cfile-class"></a>CFile-Klasse

Die Basisklasse für Microsoft Foundation Class-Dateiklassen.

## <a name="syntax"></a>Syntax

```
class CFile : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFile::CFile](#cfile)|Erstellt eine `CFile` Objekt aus einem Handle Pfad- oder Dateiname.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFile::Abort](#abort)|Schließt eine Datei wird ignoriert, alle Warnungen und Fehler.|
|[CFile::Close](#close)|Schließt eine Datei, und löscht das Objekt.|
|[CFile::Duplicate](#duplicate)|Erstellt ein doppeltes Objekt, das basierend auf diese Datei an.|
|[CFile::Flush](#flush)|Leert alle Daten noch geschrieben werden.|
|[CFile::GetFileName](#getfilename)|Ruft den Dateinamen der ausgewählten Datei ab.|
|[CFile::GetFilePath](#getfilepath)|Ruft den vollständigen Pfad der ausgewählten Datei ab.|
|[CFile::GetFileTitle](#getfiletitle)|Ruft den Titel der ausgewählten Datei ab.|
|[CFile::GetLength](#getlength)|Ruft die Länge der Datei ab.|
|[CFile::GetPosition](#getposition)|Ruft die aktuelle Dateizeiger ab.|
|[CFile::GetStatus](#getstatus)|Ruft den Status der geöffneten Datei oder in der statischen Version ab, ruft den Status der angegebenen Datei (statische virtuelle Funktion) ab.|
|[CFile::LockRange](#lockrange)|Sperrt einen Bereich von Bytes in einer Datei an.|
|[CFile::Open](#open)|Sichere öffnet eine Datei mit einer Option zum Testen der Fehler ein.|
|[CFile::Read](#read)|Lesevorgänge (gepufferten) Daten aus einer Datei an die aktuelle Dateiposition.|
|[CFile::Remove](#remove)|Löscht die angegebene Datei (statische Funktion).|
|[CFile::Rename](#rename)|Benennt die angegebene Datei (statische Funktion).|
|[CFile::Seek](#seek)|Positioniert die Dateizeiger für den aktuellen.|
|[CFile::SeekToBegin](#seektobegin)|Positioniert den Dateizeiger für aktuelle am Anfang der Datei an.|
|[CFile::SeekToEnd](#seektoend)|Positioniert den aktuellen Dateizeiger am Ende der Datei an.|
|[CFile::SetFilePath](#setfilepath)|Legt den vollständigen Pfad der ausgewählten Datei fest.|
|[CFile::SetLength](#setlength)|Ändert die Länge der Datei an.|
|[CFile::SetStatus](#setstatus)|Setzt den Status der angegebenen Datei (statische virtuelle Funktion).|
|[CFile::UnlockRange](#unlockrange)|Hebt die Sperre eines Bereichs von Bytes in einer Datei.|
|[CFile::Write](#write)|Schreibvorgänge (gepufferten) Daten in einer Datei, die die aktuelle Dateiposition an.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CFile::operator HANDLE](#operator_handle)|Ein Handle für ein `CFile` Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFile::hFileNull](#hfilenull)|Bestimmt, ob die `CFile` Objekt verfügt über ein gültiges Handle.|
|[CFile::m_hFile](#m_hfile)|In der Regel enthält das Betriebssystem-Dateihandle.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt.|

## <a name="remarks"></a>Hinweise

Es bietet direkt ungepufferte, binäre Datenträger-e/a-Dienste und indirekt Textdateien und Speicher über die abgeleiteten Klassen unterstützt. `CFile` funktioniert in Verbindung mit der `CArchive` Klasse zur Serialisierung von Objekten von Microsoft Foundation Class-Unterstützung.

Die hierarchische Beziehung zwischen dieser Klasse und die abgeleiteten Klassen kann Ihr Programm alle Dateiobjekte über polymorphen auszuführende `CFile` Schnittstelle. Eine Arbeitsspeicherdatei verhält sich z. B. wie eine Datenträgerdatei verwendet wird.

Verwendung `CFile` und ihrer abgeleiteten Klassen für allgemeine Zwecke Datenträger-e/a. Verwendung `ofstream` oder andere Microsoft-Iostream-Klassen für formatierten Text in eine Datei gesendet.

Datei auf einem Datenträger wird in der Regel automatisch geöffnet `CFile` Konstruktion und Zerstörung von geschlossenen auf. Statische Memberfunktionen können Sie des Status einer Datei abzufragen, ohne die Datei zu öffnen.

Weitere Informationen zur Verwendung von `CFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in die *Run-Time Library Reference*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="abort"></a>  CFile::Abort

Schließt die Datei, die diesem Objekt zugeordnet, und ist die Datei zum Lesen oder Schreiben nicht verfügbar.

```
virtual void Abort();
```

### <a name="remarks"></a>Hinweise

Wenn Sie vor dem Zerstören des Objekts nicht die Datei geschlossen haben, wird Sie von der Destruktor für Sie geschlossen.

Bei der Behandlung von Ausnahmen, `CFile::Abort` unterscheidet sich von `CFile::Close` in zwei wichtigen Punkten. Zunächst wird die `Abort` Funktion wird eine Ausnahme nicht bei Fehlern ausgelöst werden, da der Fehler ignoriert werden, indem `Abort`. Zweitens `Abort` nicht **ASSERT** sollte diese Datei nicht geöffnet wurde oder wurde bereits geschlossen.

Wenn Sie verwendet **neue** Zuweisen der `CFile` Objekt auf dem Heap, und Sie sie löschen müssen, nach dem Schließen der Datei. `Abort` Legt `m_hFile` zu `CFile::hFileNull`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

##  <a name="cfile"></a>  CFile::CFile

Erstellt und initialisiert ein `CFile`-Objekt.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parameter

*hFile*<br/>
Handle einer Datei zum Anhängen an das `CFile`-Objekt.

*lpszFileName*<br/>
Relativer oder vollständiger Pfad einer Datei zum Anhängen an das `CFile`-Objekt.

*nOpenFlags*<br/>
Bitweise Kombination (OR) der Dateizugriffsoptionen für die angegebene Datei. Mögliche Optionen finden Sie im Abschnitt "Hinweise".

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Die folgenden fünf Tabellen enthalten die möglichen Optionen für die *nOpenFlags* Parameter.

Wählen Sie eine der folgenden Dateizugriffsmodus-Optionen. Der standardmäßige Dateizugriffsmodus ist `CFile::modeRead`, wobei es sich um einen schreibgeschützten Modus handelt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::modeRead`|Fordert nur Lesezugriff an.|
|`CFile::modeWrite`|Fordert nur Schreibzugriff an.|
|`CFile::modeReadWrite`|Fordert Lese- und Schreibzugriff an.|

Wählen Sie eine der folgenden Zeichenmodus-Optionen.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::typeBinary`|Legt den Binärmodus fest (nur in abgeleiteten Klassen verwendet).|
|`CFile::typeText`|Legt den Textmodus mit spezieller Verarbeitung für Wagenrücklauf-Return-Zeilenvorschub-Paare (nur in abgeleiteten Klassen verwendet).|
|`CFile::typeUnicode`|Legt den Unicode-Modus fest (nur in abgeleiteten Klassen verwendet). Text wird im Unicode-Format in die Datei geschrieben, wenn die Anwendung in einer Unicode-Konfiguration erstellt wurde. Es wird keine BOM in die Datei geschrieben.|

Wählen Sie eine der folgenden Dateifreigabemodus-Optionen. Der standardmäßige Dateifreigabemodus ist `CFile::shareExclusive`, wobei es sich um einen exklusiven Modus handelt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::shareDenyNone`|Keine Freigabebeschränkungen.|
|`CFile::shareDenyRead`|Verweigert allen anderen Lesezugriff.|
|`CFile::shareDenyWrite`|Verweigert allen anderen Schreibzugriff.|
|`CFile::shareExclusive`|Verweigert allen anderen Lese- und Schreibzugriff.|

Wählen Sie die erste oder beide Dateierstellungsmodus-Optionen. Der standardmäßige Dateierstellungsmodus ist `CFile::modeNoTruncate`, wobei es sich um "offen vorhanden" handelt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::modeCreate`|Erstellt eine neue Datei an, wenn keine Datei vorhanden ist. Wenn die Datei bereits vorhanden ist, wird es überschrieben, und zunächst auf die Länge Null festgelegt.|
|`CFile::modeNoTruncate`|Erstellt eine neue Datei, wenn keine Datei existiert. Wenn die Datei bereits vorhanden ist, wird sie anderenfalls an das `CFile`-Objekt angehängt.|

Wählen Sie die folgenden Datei-Cache-Optionen wie beschrieben. Standardmäßig verwendet das System ein allgemeines Cache-Schema, das nicht als Option verfügbar ist.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::osNoBuffer`|Das System verwendet keinen Zwischen-Cache für die Datei. Diese Option bricht die beiden folgenden Optionen ab.|
|`CFile::osRandomAccess`|Der Datei-Cache wird für wahlfreien Zugriff optimiert. Verwenden Sie nicht diese Option und die sequenzielle Scan-Option.|
|`CFile::osSequentialScan`|Der Datei-Cache wird für sequenziellen Zugriff optimiert. Verwenden Sie nicht diese Option und die Option für wahlfreien Zugriff.|
|`CFile::osWriteThrough`|Schreibvorgänge werde ohne Verzögerung ausgeführt.|

Wählen Sie die folgende Sicherheitsoption, um zu verhindern, dass der Dateihandle übergeben wird. Standardmäßig können alle neuen untergeordneten Prozesse den Dateihandle verwenden.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::modeNoInherit`|Verhindert, dass untergeordnete Prozesse den Dateihandle verwenden.|

Der Standardkonstruktor initialisiert Member, hängt jedoch keine Datei an das `CFile`-Objekt an. Nach der Verwendung dieses Konstruktors, der [CFile::Open](#open) Methode, um eine Datei öffnen, und fügen Sie ihn auf die `CFile` Objekt.

Der Konstruktor mit einem Parameter initialisiert Member und hängt eine vorhandene Datei an das `CFile`-Objekt an.

Der Konstruktor mit zwei Parametern initialisiert Member und versucht, die angegebene Datei zu öffnen. Wenn der Konstruktor die angegebene Datei erfolgreich öffnet, wird die Datei an das `CFile`-Objekt angehängt; anderenfalls löst der Konstruktor einen Zeiger auf ein `CInvalidArgException`-Objekt aus. Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

Wenn ein `CFile`-Objekt eine angegebene Datei erfolgreich öffnet, wird diese Datei automatisch geschlossen, wenn das `CFile`-Objekt zerstört wird; anderenfalls müssen Sie die Datei explizit schließen, wenn sie nicht mehr an das `CFile`-Objekt angehängt ist.

### <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung einer `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

##  <a name="close"></a>  CFile::Close

Schließt die Datei, die diesem Objekt zugeordnet, und ist die Datei zum Lesen oder Schreiben nicht verfügbar.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Wenn Sie vor dem Zerstören des Objekts nicht die Datei geschlossen haben, wird Sie von der Destruktor für Sie geschlossen.

Wenn Sie verwendet **neue** Zuweisen der `CFile` Objekt auf dem Heap, und Sie sie löschen müssen, nach dem Schließen der Datei. `Close` Legt `m_hFile` zu `CFile::hFileNull`.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFile::CFile](#cfile).

##  <a name="duplicate"></a>  CFile::Duplicate

Erstellt ein Duplikat `CFile` Objekt für eine angegebene Datei.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Duplikat `CFile` Objekt.

### <a name="remarks"></a>Hinweise

Dies entspricht der C-Laufzeitfunktion `_dup`.

##  <a name="flush"></a>  CFile::Flush

Erzwingt, dass alle Daten verbleiben in der Dateipuffer, in die Datei geschrieben werden.

```
virtual void Flush();
```

### <a name="remarks"></a>Hinweise

Die Verwendung von `Flush` garantiert keine Leerung `CArchive` Puffer. Wenn Sie ein Archiv verwenden, rufen Sie [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) erste.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFile::SetFilePath](#setfilepath).

##  <a name="getfilename"></a>  CFile::GetFileName

Rufen Sie diese Memberfunktion auf den Namen einer angegebenen Datei abrufen.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name der Datei.

### <a name="remarks"></a>Hinweise

Z. B. beim Aufruf `GetFileName` zum Generieren einer Nachricht an den Benutzer über die Datei `c:\windows\write\myfile.wri`, dem Dateinamen, `myfile.wri`, zurückgegeben wird.

Rufen Sie den vollständigen Pfad der Datei, einschließlich Name, zurückzugebenden [GetFilePath](#getfilepath). Den Titel der Datei zurückgegeben ( `myfile`), rufen Sie [GetFileTitle](#getfiletitle).

### <a name="example"></a>Beispiel

Dieses Codefragment wird das SYSTEM geöffnet. INI-Datei in Ihrem WINDOWS-Verzeichnis. Wenn gefunden, im Beispiel wird der Name und Pfad und Titel drucken möchten wie in der Ausgabe dargestellt:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

##  <a name="getfilepath"></a>  CFile::GetFilePath

Rufen Sie diese Memberfunktion um den vollständigen Pfad einer angegebenen Datei abzurufen.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Rückgabewert

Der vollständige Pfad der angegebenen Datei.

### <a name="remarks"></a>Hinweise

Z. B. beim Aufruf `GetFilePath` zum Generieren einer Nachricht an den Benutzer über die Datei `c:\windows\write\myfile.wri`, Dateipfad `c:\windows\write\myfile.wri`, zurückgegeben wird.

Nur der Name der Datei zurückgegeben (`myfile.wri`), rufen Sie [GetFileName](#getfilename). Den Titel der Datei zurückgegeben (`myfile`), rufen Sie [GetFileTitle](#getfiletitle).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetFileName](#getfilename).

##  <a name="getfiletitle"></a>  CFile::GetFileTitle

Rufen Sie diese Memberfunktion um den Dateititel (Anzeigename) für die Datei abzurufen.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Rückgabewert

Der Titel des zugrunde liegenden Datei.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) um den Titel der Datei abzurufen. Wenn erfolgreich, wird die Methode die Zeichenfolge, die das System verwenden würden, um den Dateinamen für den Benutzer anzuzeigen. Andernfalls ruft die Methode [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) zum Abrufen des Dateinamens (einschließlich der Dateierweiterung) der zugrunde liegenden Datei. Aus diesem Grund wird die Dateierweiterung nicht immer in die zurückgegebene Titelzeichenfolge enthalten sein. Weitere Informationen finden Sie unter [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) und [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) im Windows SDK.

Rufen Sie den vollständigen Pfad der Datei, einschließlich Name, zurückzugebenden [GetFilePath](#getfilepath). Rufen Sie zum Zurückgeben nur der Name der Datei [GetFileName](#getfilename).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetFileName](#getfilename).

##  <a name="getlength"></a>  CFile::GetLength

Ruft die aktuelle logische Länge der Datei in Bytes ab.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der Datei.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

##  <a name="getposition"></a>  CFile::GetPosition

Ruft den aktuellen Wert des Zeigers Datei, die bei nachfolgenden Aufrufen verwendet werden können `Seek`.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Der Dateizeiger.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

##  <a name="getstatus"></a>  CFile:: GetStatus

Diese Methode ruft Statusinformationen, die im Zusammenhang mit einer bestimmten `CFile` Objektinstanz oder der einem angegebenen Dateipfad.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*rStatus*<br/>
Ein Verweis auf eine vom Benutzer bereitgestelltes `CFileStatus` -Struktur, die die Informationen erhält. Die `CFileStatus` Struktur enthält die folgenden Felder:

- `CTime m_ctime` Das Datum und Uhrzeit der Erstellung die Datei.

- `CTime m_mtime` Das Datum und Uhrzeit der letzten der Datei Änderung.

- `CTime m_atime` Das Datum und Uhrzeit des letzten Zugriffs auf die Datei zum Lesen.

- `ULONGLONG m_size` Die logische Größe der Datei in Bytes, so wie durch den Befehl "DIR" gemeldet.

- `BYTE m_attribute` Das Attribut Byte der Datei.

- `char m_szFullName[_MAX_PATH]` Legen der absolute Dateinamen in das Windows-Zeichen.

*lpszFileName*<br/>
Eine Zeichenfolge in das Windows-Zeichen festgelegt, den Pfad zur gewünschten Datei. Der Pfad kann relativ oder absolut sein, oder es kann einen Netzwerknamen für den Pfad enthalten.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="return-value"></a>Rückgabewert

True, wenn die Statusinformationen für die angegebene Datei erfolgreich abgerufen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Die nicht statische Version der `GetStatus` ruft Statusinformationen der geöffneten Datei zugeordneten der angegebenen `CFile` Objekt.  Die statische Version der `GetStatus` ohne tatsächlich die Datei wird der Dateistatus aus einem angegebenen Dateipfad abgerufen. Dies ist hilfreich beim Testen das Vorhandensein und die Zugriffsrechte einer Datei.

Die `m_attribute` Mitglied der `CFileStatus` Struktur bezieht sich auf die Datei-Attribut. Die `CFile` -Klasse stellt die **Attribut** Enumeration zu geben, damit die Dateiattribute symbolisch angegeben werden können:

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

##  <a name="hfilenull"></a>  CFile::hFileNull

Bestimmt das Vorhandensein eines gültigen Dateihandles für die `CFile` Objekt.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Hinweise

Diese Konstante wird verwendet, um zu bestimmen, ob die `CFile` Objekt verfügt über einen gültigen Dateihandles.

Das folgende Beispiel zeigt diesen Vorgang:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

##  <a name="lockrange"></a>  CFile::LockRange

Sperrt einen Bereich von Bytes in einer geöffneten Datei, die eine Ausnahme auszulösen, wenn die Datei bereits gesperrt ist.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parameter

*dwPos*<br/>
Der Byteoffset des Anfangs des zu sperrenden Bytebereichs.

*dwCount*<br/>
Die Anzahl der Bytes in der zu sperrenden Bereichs.

### <a name="remarks"></a>Hinweise

Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als einer Region in einer Datei sperren, aber keine sich überschneidenden Bereiche sind zulässig.

Wenn Sie die Region entsperrt haben, verwenden die `UnlockRange` Member-Funktion der Bytebereich muss genau in der Region, die zuvor gesperrt wurde, entsprechen. Die `LockRange` Funktion benachbarte Bereiche nicht zusammen, wenn zwei gesperrte Bereiche aneinandergrenzen, müssen Sie jede Region separat entsperrt.

> [!NOTE]
>  Diese Funktion ist nicht verfügbar für die `CMemFile`-abgeleitete Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="m_hfile"></a>  CFile::m_hFile

Enthält das Betriebssystem-Dateihandle für eine geöffnete Datei.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Hinweise

`m_hFile` ist eine öffentliche Variable vom Typ "uint". Es enthält `CFile::hFileNull` (eine leere Datei operating System-unabhängigen Indicator) Wenn das Handle nicht zugewiesen wurde.

Verwenden von `m_hFile` wird nicht empfohlen, da die abgeleitete Klasse des Elements Bedeutung abhängt. `m_hFile` erfolgt einen öffentlichen Member der Einfachheit halber bei der Unterstützung von nicht polymorphen der Klasse zu verwenden.

##  <a name="m_ptm"></a>  CFile::m_pTM

Zeiger auf eine `CAtlTransactionManager` Objekt.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Hinweise

##  <a name="open"></a>  CFile::Open

Überladen. `Open` Dient zur Verwendung mit der standardmäßigen `CFile` Konstruktor.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann es sich um Relative, Absolute oder den Namen eines Netzwerks (UNC) sein.

*nOpenFlags*<br/>
UINT, die der Datei-Freigabe und Modus definiert. Es gibt die Aktion an, der beim Öffnen der Datei an. Sie können Optionen kombinieren, mit dem bitweisen OR-( **&#124;** ) Operator. Ein zugriffsberechtigungseintrag und ein Freigabe-Option sind erforderlich. die `modeCreate` und `modeNoInherit` Modi sind optional. Finden Sie unter den [CFile](#cfile) Konstruktor für eine Liste der Optionen.

*pError*<br/>
Ein Zeiger auf eine vorhandene Datei-Ausnahmeobjekt, das den Status eines fehlgeschlagenen Vorgangs empfangen wird.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das geöffnete erfolgreich war; andernfalls 0. Die *pError* Parameter ist nur sinnvoll, wenn 0 zurückgegeben wird.

### <a name="remarks"></a>Hinweise

Die beiden Funktionen bilden eine "sichere" Methode zum Öffnen einer Datei, in denen ein Fehler für eine normale, erwartete Bedingung ist.

Während der `CFile` Konstruktors löst eine Ausnahme in einem Fehlerzustand `Open` für fehlerbedingungen den Wert FALSE zurück. `Open` können immer noch Initialisieren einer [CFileException](../../mfc/reference/cfileexception-class.md) Objekt, das den Fehler, jedoch zu beschreiben. Wenn Sie angeben, nicht die *pError* -Parameter oder übergeben Sie NULL für *pError*, `Open` "false" zurück und keine Ausnahme auslöst eine `CFileException`. Wenn Sie einen Zeiger auf eine vorhandene übergeben `CFileException`, und `Open` einen Fehler erkennt, die Funktion füllt es mit Informationen, die den Fehler beschreibt. In der keine Groß-/Kleinschreibung wird `Open` löst eine Ausnahme aus.

Die folgende Tabelle beschreibt die möglichen Ergebnisse `Open`.

|`pError`|Fehler:|Rückgabewert|CFileException-Inhalt|
|--------------|------------------------|------------------|----------------------------|
|NULL|Nein|true|n/v|
|PTR `CFileException`|Nein|true|unverändert|
|NULL|Ja|false|n/v|
|PTR `CFileException`|Ja|false|Initialisiert, um Fehler zu beschreiben|

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

##  <a name="operator_handle"></a>  CFile::operator HANDLE

Verwenden Sie diesen Operator übergeben Sie ein Handle für ein `CFile` -Objekt Funktionen wie z. B. [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) und [GetFileTime](/windows/desktop/api/fileapi/nf-fileapi-getfiletime) erwarten, dass eine `HANDLE`.

```
operator HANDLE() const;
```

##  <a name="read"></a>  CFile:: Read

Liest Daten in einen Puffer aus der Datei zugeordneten der `CFile` Objekt.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Zeiger auf den Benutzer bereitgestellten Puffer, der die Daten zu empfangen, die aus der Datei gelesen werden.

*nCount*<br/>
Die maximale Anzahl an Bytes, aus der Datei gelesen werden. Für Dateien, Textmodus werden die Carriage Return-Zeilenvorschub-Paare als einzelne Zeichen gezählt.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der in den Puffer übertrageben Bytes. Beachten Sie, dass für alle `CFile` Klassen, ist der zurückgegebene Wert möglicherweise weniger als *nCount* Wenn am Ende der Datei erreicht wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Ein weiteres Beispiel finden Sie unter [CFile::Open](#open).

##  <a name="remove"></a>  CFile::Remove

Diese statischen Funktion löscht die durch den Pfad angegebene Datei.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein und darf einen Netzwerknamen an.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Es wird ein Verzeichnis nicht entfernt.

Die `Remove` Memberfunktion löst eine Ausnahme aus, wenn die verbundenen Datei geöffnet ist, oder wenn die Datei kann nicht entfernt werden. Dies ist gleichbedeutend mit dem Befehl DEL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

##  <a name="rename"></a>  CFile::Rename

Diese statischen Funktion benennt die angegebene Datei.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszOldName*<br/>
Der alte Pfad.

*lpszNewName*<br/>
Der neue Pfad.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Verzeichnisse können nicht umbenannt werden. Dies ist äquivalent zum Befehl REN.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

##  <a name="seek"></a>  CFile::Seek

Positioniert den Dateizeiger in einer geöffneten Datei.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Parameter

*lOff*<br/>
Die Anzahl der Bytes, den Dateizeiger zu verschieben. Positive Werte verschieben den Dateizeiger am Ende der Datei; negative Werte verschieben den Dateizeiger zum Anfang der Datei.

*nFrom*<br/>
Die Position aus suchen. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.

### <a name="return-value"></a>Rückgabewert

Die Position des Dateizeigers, wenn die Methode erfolgreich war; Andernfalls ist der Rückgabewert undefiniert und einen Zeiger auf eine `CFileException` Ausnahme ausgelöst.

### <a name="remarks"></a>Hinweise

Die folgende Tabelle enthält die möglichen Werte für die *nWenn* Parameter.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::begin`|Ab dem Anfang der Datei zu suchen.|
|`CFile::current`|Von der aktuellen Position des Dateizeigers zu suchen.|
|`CFile::end`|Am Ende der Datei zu suchen.|

Wenn eine Datei geöffnet wird, wird der Dateizeiger am 0 (null) den Anfang der Datei positioniert.

Sie können den Dateizeiger an eine Position hinter dem Ende einer Datei festlegen. Wenn Sie dies tun, steigert die Größe der Datei nicht, bis Sie in der Datei zu schreiben.

Der Ausnahmehandler für diese Methode muss das Ausnahmeobjekt löschen, nachdem die Ausnahme verarbeitet wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

##  <a name="seektobegin"></a>  CFile::SeekToBegin

Legt den Wert der Dateizeiger am Anfang der das fest.

```
void SeekToBegin();
```

### <a name="remarks"></a>Hinweise

`SeekToBegin()` entspricht `Seek( 0L, CFile::begin )`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="seektoend"></a>  CFile::SeekToEnd

Legt den Wert der Dateizeiger am logischen Ende der Datei fest.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Rückgabewert

Die Länge der Datei in Byte.

### <a name="remarks"></a>Hinweise

`SeekToEnd()` entspricht `CFile::Seek( 0L, CFile::end )`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="setfilepath"></a>  CFile::SetFilePath

Aufrufen dieser Funktion können Sie den Pfad der Datei angeben. Wenn der Pfad einer Datei nicht verfügbar bei ist z. B. eine [CFile](../../mfc/reference/cfile-class.md) -Objekt erstellt wird, rufen Sie `SetFilePath` bereitstellen.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parameter

*lpszNewName*<br/>
Zeiger auf eine Zeichenfolge, die den neuen Pfad angibt.

### <a name="remarks"></a>Hinweise

> [!NOTE]
> `SetFilePath` nicht öffnen Sie die Datei oder erstellen Sie die Datei; es einfach ordnet die `CFile` Objekt mit einem Pfadnamen, die dann verwendet werden kann.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

##  <a name="setlength"></a>  CFile::SetLength

Rufen Sie diese Funktion, um die Länge der Datei zu ändern.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Parameter

*dwNewLen*<br/>
Die gewünschte Länge der Datei in Bytes. Dieser Wert kann größer oder kleiner als die aktuelle Länge der Datei sein. Die Datei wird je nach Bedarf abgeschnitten oder erweitert werden.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Mit `CMemFile`, diese Funktion auslösen konnte eine `CMemoryException` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

##  <a name="setstatus"></a>  CFile::SetStatus

Setzt den Status der Speicherort dieser Datei zugeordneten Datei.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein und darf einen Netzwerknamen an.

*Status*<br/>
Der Puffer, der die neue Statusinformationen enthält. Rufen Sie die `GetStatus` Bibliotheksvorlage Memberfunktion die `CFileStatus` Struktur, deren aktuelle Werte, und ändern Sie dann nach Bedarf. Wenn ein Wert 0 ist, wird der entsprechende Statuselement nicht aktualisiert. Finden Sie unter den [GetStatus](#getstatus) Member-Funktion, eine Beschreibung der `CFileStatus` Struktur.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Ändern, um die Zeit, die `m_mtime` Feld *Status*.

Beachten Sie, dass wenn Sie einen Aufruf von vornehmen `SetStatus` Versuch so ändern Sie nur die Attribute der Datei, und die `m_mtime` Member der Struktur der Datei Status ungleich NULL ist, die Attribute können ebenfalls davon betroffen sein (ändern die Zeit, die Zeitstempel kann Nebeneffekte haben, auf die Attribute). Wenn Sie nur die Attribute der Datei ändern möchten, legen Sie zuerst die `m_mtime` Member der Struktur der Datei-Status auf 0 (null), und stellen Sie dann einen Aufruf von `SetStatus`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

##  <a name="unlockrange"></a>  CFile::UnlockRange

Hebt die Sperre eines Bereichs von Bytes in einer geöffneten Datei.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parameter

*dwPos*<br/>
Der Byteoffset des Anfangs des zu entsperrenden Bytebereichs.

*dwCount*<br/>
Die Anzahl der Bytes in der zu entsperrenden Bereichs.

### <a name="remarks"></a>Hinweise

Finden Sie in der Beschreibung der [LockRange](#lockrange) Memberfunktion Details.

> [!NOTE]
>  Diese Funktion ist nicht verfügbar für die `CMemFile`-abgeleitete Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="write"></a>  CFile::Write

Schreibt Daten aus einem Puffer in die zugeordnete Datei die `CFile` Objekt.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger auf den Benutzer bereitgestellten Puffer mit den Daten, auf die Datei geschrieben werden soll.

*nCount*<br/>
Die Anzahl der Bytes, aus dem Puffer übertragen werden sollen. Für Dateien, Textmodus werden die Carriage Return-Zeilenvorschub-Paare als einzelne Zeichen gezählt.

### <a name="remarks"></a>Hinweise

`Write` löst eine Ausnahme als Reaktion auf verschiedene Bedingungen, einschließlich der Datenträger voll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Darüber hinaus finden Sie in den Beispielen für [CFile::CFile](#cfile) und [CFile::Open](#open).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)
