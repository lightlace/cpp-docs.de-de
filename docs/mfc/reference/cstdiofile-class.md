---
title: CStdioFile-Klasse
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 4b667f4121d92863335befda3a7beef74f29ad1a
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177488"
---
# <a name="cstdiofile-class"></a>CStdioFile-Klasse

Stellt eine C-Laufzeit-streamdatei dar, wie Sie durch die Lauf Zeitfunktion von " [f Open](../../c-runtime-library/reference/fopen-wfopen.md)" geöffnet wurde.

## <a name="syntax"></a>Syntax

```
class CStdioFile : public CFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|Erstellt ein `CStdioFile` -Objekt aus einem Pfad-oder Dateizeiger.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStdioFile::Open](#open)|Überladen. Open ist für die Verwendung mit dem Standardkonstruktor `CStdioFile` konzipiert (überschreibt [CFile:: Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile::ReadString](#readstring)|Liest eine einzelne Textzeile.|
|[CStdioFile::Seek](#seek)|Positioniert den aktuellen Dateizeiger.|
|[CStdioFile::WriteString](#writestring)|Schreibt eine einzelne Textzeile.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Enthält einen Zeiger auf eine geöffnete Datei.|

## <a name="remarks"></a>Hinweise

Streamdateien werden gepuffert und können entweder im Textmodus (Standard) oder im Binärmodus geöffnet werden.

Der Textmodus stellt eine spezielle Verarbeitung für Wagen Rücklauf-Zeilenvorschub Paare bereit. Wenn Sie einen Zeilenvorschub (Zeilenvorschub Zeichen (0x0A) in ein `CStdioFile` textmodusobjekt schreiben, wird das Bytepaar (0x0D, 0x0A) an die Datei gesendet. Wenn Sie lesen, wird das Bytepaar (0x0D, 0x0A) in ein einzelnes 0x0A-Byte übersetzt.

Die [CFile](../../mfc/reference/cfile-class.md) -Funktionen " [Duplicate](../../mfc/reference/cfile-class.md#duplicate)", " [lockrange](../../mfc/reference/cfile-class.md#lockrange)" und " [unlockrange](../../mfc/reference/cfile-class.md#unlockrange) " werden für `CStdioFile`nicht unterstützt.

Wenn Sie diese Funktionen auf einem `CStdioFile`-Element aufzurufen, wird eine [cnotsupportedexception-Ausnahme](../../mfc/reference/cnotsupportedexception-class.md)angezeigt.

Weitere Informationen zur Verwendung von `CStdioFile`finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Datei Behandlung](../../c-runtime-library/file-handling.md) in der *Lauf Zeit Bibliotheks Referenz*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cstdiofile"></a>CStdioFile:: CStdioFile

Erstellt und initialisiert ein `CStdioFile`-Objekt.

```
CStdioFile();
CStdioFile(CAtlTransactionManager* pTM);
CStdioFile(FILE* pOpenStream);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parameter

*pOpenStream*<br/>
Gibt den Dateizeiger an, der durch einen Aufruf der C-Lauf Zeitfunktion [fopen](../../c-runtime-library/reference/fopen-wfopen.md)zurückgegeben wird.

*lpszFileName*<br/>
Gibt eine Zeichenfolge an, die den Pfad zur gewünschten Datei angibt. Der Pfad kann relativ oder absolut sein.

*nOpenFlags*<br/>
Gibt Optionen für die Dateierstellung, Dateifreigabe und Datei Zugriffs Modi an. Sie können mehrere Optionen mithilfe des bitweisen or ( **|** )-Operators angeben.

Eine Option für den Datei Zugriffsmodus ist erforderlich. andere Modi sind optional. Eine Liste der Optionen für den Modus und andere Flags finden Sie unter [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile) . In MFC, Version 3,0 und höher, sind Freigabe-Flags zulässig.

*pTM*<br/>
Zeiger auf das Objekt "-Objekt".

### <a name="remarks"></a>Hinweise

Der Standardkonstruktor fügt keine Datei an das `CStdioFile` -Objekt an. Wenn Sie diesen Konstruktor verwenden, müssen Sie die `CStdioFile::Open` -Methode verwenden, um eine Datei zu öffnen und `CStdioFile` an das-Objekt anzufügen.

Der Konstruktor mit einem Parameter fügt dem `CStdioFile` -Objekt einen geöffneten Datei Datenstrom hinzu. Zulässige Zeiger Werte sind die vordefinierten Eingabe-/ausgabedateizeiger *stdin*, *stdout*oder *stderr*.

Der zwei-Parameter-Konstruktor erstellt `CStdioFile` ein-Objekt und öffnet die entsprechende Datei mit dem angegebenen Pfad.

Wenn Sie NULL für *popenstream* oder *lpszfilename*übergeben, löst der Konstruktor eine `CInvalidArgException*`aus.

Wenn die Datei nicht geöffnet oder erstellt werden kann, löst der Konstruktor `CFileException*`eine aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>CStdioFile:: m_pStream

Der `m_pStream` Datenmember ist der Zeiger auf eine geöffnete Datei, wie von der C-Lauf Zeitfunktion `fopen`zurückgegeben.

```
FILE* m_pStream;
```

### <a name="remarks"></a>Hinweise

Der Wert ist NULL, wenn die Datei noch nicht geöffnet oder geschlossen wurde.

##  <a name="open"></a>CStdioFile:: Open

Überladen. Open ist für die Verwendung mit dem Standardkonstruktor `CStdioFile` konzipiert.

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
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein.

*nOpenFlags*<br/>
Freigabe-und Zugriffsmodus. Gibt die Aktion an, die beim Öffnen der Datei ausgeführt werden soll. Optionen können mithilfe des bitweisen OR-Operators (&#124;) kombiniert werden. Eine Zugriffsberechtigung und eine Freigabe Option sind erforderlich. die Modi "modeCreate" und "mubezeichgeerbt" sind optional.

*pError*<br/>
Ein Zeiger auf ein vorhandenes Datei Ausnahme Objekt, das den Status einer fehlgeschlagenen Operation empfängt.

*pTM*<br/>
Zeiger auf ein `CAtlTransactionManager` -Objekt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

##  <a name="readstring"></a>CStdioFile:: infoString

Liest Textdaten aus der Datei, die dem `CStdioFile` -Objekt zugeordnet ist, bis zu einer Beschränkung von *nmax*-1 Zeichen in einen Puffer.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
Gibt einen Zeiger auf einen vom Benutzer bereitgestellten Puffer an, der eine NULL-terminierte Text Zeichenfolge empfängt.

*nMax*<br/>
Gibt die maximale Anzahl der zu lesenden Zeichen an, wobei das abschließende Null-Zeichen nicht gezählt wird.

*rString*<br/>
Ein Verweis auf ein `CString` -Objekt, das die Zeichenfolge enthält, wenn die Funktion zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Puffer, der die Textdaten enthält. NULL, wenn das Dateiende erreicht wurde, ohne dass Daten gelesen wurden. oder, wenn es sich um einen booleschen Wert handelt, false, wenn das Dateiende erreicht wurde, ohne Daten zu lesen.

### <a name="remarks"></a>Hinweise

Das Lesen wird durch das erste Zeilen Trennzeichen beendet. Wenn in diesem Fall weniger als *nmax*-1 Zeichen gelesen wurden, wird ein Zeilen vorzeichenfolge im Puffer gespeichert. In jedem Fall wird ein NULL-Zeichen (' \ 0 ') angefügt.

[CFile:: Read](../../mfc/reference/cfile-class.md#read) ist auch für die textmoduseingabe verfügbar, wird jedoch nicht bei einem Wagen Rücklauf/Zeilenvorschub-Paar beendet.

> [!NOTE]
>  Die `CString` -Version dieser Funktion entfernt den `'\n'` , sofern vorhanden, die LPTSTR-Version nicht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>CStdioFile:: Seek

Positioniert den Zeiger in einer zuvor geöffneten Datei.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Parameter

*lOff*<br/>
Anzahl von Bytes zum Verschieben des Zeigers.

*nFrom*<br/>
Zeiger Bewegungsmodus. Muss einen der folgenden Werte aufweisen:

- `CFile::begin`: Verschiebt den Dateizeiger aus dem Anfang der Datei nach oben.

- `CFile::current`: Verschiebt den Dateizeiger aus der aktuellen Position in der Datei.

- `CFile::end`: Verschieben Sie den Datei Zeiger mit dem Dateizeiger von dem Ende der Datei. Beachten Sie, dass bei der Suche in der vorhandenen Datei " *lOff* " negativ sein muss. positive Werte werden nach dem Ende der Datei gesucht.

### <a name="return-value"></a>Rückgabewert

Wenn die angeforderte Position zulässig ist `Seek` , wird der neue Byte Offset vom Anfang der Datei zurückgegeben. Andernfalls ist der Rückgabewert nicht definiert, und `CFileException` es wird ein-Objekt ausgelöst.

### <a name="remarks"></a>Hinweise

Die `Seek` -Funktion ermöglicht den zufälligen Zugriff auf den Inhalt einer Datei, indem der Zeiger auf einen angegebenen Betrag (absolut oder relativ) verschoben wird. Während der Suche werden tatsächlich keine Daten gelesen. Wenn die angeforderte Position größer als die Größe der Datei ist, wird die Dateilänge auf diese Position erweitert, und es wird keine Ausnahme ausgelöst.

Wenn eine Datei geöffnet wird, wird der Dateizeiger am Offset 0, dem Anfang der Datei positioniert.

Diese Implementierung von `Seek` basiert auf der-Funktion `fseek`der Lauf Zeit Bibliothek (CRT). Es gibt mehrere Einschränkungen bei der Verwendung von `Seek` in Datenströmen, die im Textmodus geöffnet wurden. Weitere Informationen finden Sie unter [_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie `Seek` verwendet wird, um den Zeiger 1000 Bytes vom Anfang `cfile` der Datei zu verschieben. Beachten Sie `Seek` , dass keine Daten liest, daher müssen Sie anschließend [CStdioFile:: infoString](#readstring) zum Lesen von Daten abrufen.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>CStdioFile:: Write String

Schreibt Daten aus einem Puffer in die Datei, die dem `CStdioFile` -Objekt zugeordnet ist.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
Gibt einen Zeiger auf einen Puffer an, der eine NULL-terminierte Zeichenfolge enthält.

### <a name="remarks"></a>Hinweise

Das abschließende Null-Zeichen `\0`() wird nicht in die Datei geschrieben. Diese Methode schreibt Zeilenumbruch Zeichen in *lpsz* als Wagen Rücklauf-Zeilenvorschub-Paar in die Datei.

Wenn Sie Daten schreiben möchten, die nicht mit null-terminierten Daten in eine `CStdioFile::Write` Datei geschrieben werden, verwenden Sie oder [CFile:: Write](../../mfc/reference/cfile-class.md#write).

Diese Methode löst eine `CInvalidArgException*` aus, wenn Sie für den *lpsz* -Parameter NULL angeben.

Diese Methode löst als `CFileException*` Antwort auf Dateisystem Fehler eine aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile:: lockrange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile:: unlockrange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)
