---
title: CStdioFile-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: fd42934107591905a1bbc273ee9eec4b37e58ea7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323803"
---
# <a name="cstdiofile-class"></a>CStdioFile-Klasse

Stellt eine C-Laufzeit-streamdatei dar, von der Laufzeit-Funktion öffnen [Fopen](../../c-runtime-library/reference/fopen-wfopen.md).

## <a name="syntax"></a>Syntax

```
class CStdioFile : public CFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|Erstellt eine `CStdioFile` Objekt von einem Zeiger Pfad- oder Dateiname.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStdioFile::Open](#open)|Überladen. Öffnen Sie für die Verwendung mit der standardmäßigen vorgesehen `CStdioFile` Konstruktor (überschreibt [CFile::Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile::ReadString](#readstring)|Liest eine Textzeile an.|
|[CStdioFile::Seek](#seek)|Positioniert die Dateizeiger für den aktuellen.|
|[CStdioFile::WriteString](#writestring)|Schreibt eine Textzeile an.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Enthält einen Zeiger auf eine geöffnete Datei.|

## <a name="remarks"></a>Hinweise

Stream-Dateien werden gepuffert und können in entweder im Textmodus (Standard) oder im binärdateimodus geöffnet werden.

Text-Modus bietet speziellen Verarbeitung für Wagenrücklauf-Return-Zeilenvorschub-Paare. Wenn Sie eine neue Zeile schreiben Zeichen (0x0A) in einen Text-Modus `CStdioFile` -Objekt, das Byte-Paar (0x0D, 0x0A) an die Datei gesendet wird. Wenn Sie lesen, das Byte-Paar (0x0D, 0x0A) wird in ein einzelnes 0x0A Byte übersetzt.

Die [CFile](../../mfc/reference/cfile-class.md) Funktionen [doppelte](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), und [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) können nicht für `CStdioFile`.

Wenn Sie für diese Funktionen aufrufen einer `CStdioFile`, erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Weitere Informationen zur Verwendung von `CStdioFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in die *Run-Time Library Reference*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile

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
Gibt an, den Dateizeiger, der durch einen Aufruf an die C Run-Time-Funktion zurückgegebenen [Fopen](../../c-runtime-library/reference/fopen-wfopen.md).

*lpszFileName*<br/>
Gibt eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein.

*nOpenFlags*<br/>
Gibt Optionen für die Datei erstellen, Freigeben von Dateien und Zugriffsmodi für die Datei. Sie können mehrere Optionen angeben, mit dem bitweisen OR ( **|** ) Operator.

Ein ist Datei-Modus erforderlich; andere Modi sind optional. Finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) eine Liste der Optionen und andere Flags. In MFC, Version 3.0 und höher sind die Freigabe Flags zulässig.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt.

### <a name="remarks"></a>Hinweise

Der Standardkonstruktor wird keine Datei angefügt der `CStdioFile` Objekt. Wenn Sie diesen Konstruktor verwenden, müssen Sie verwenden die `CStdioFile::Open` Methode, um eine Datei öffnen, und fügen Sie ihn auf die `CStdioFile` Objekt.

Der Konstruktor für die einzelnen-Parameter Fügt eine geöffnete Datei-Stream, der `CStdioFile` Objekt. Zulässige Zeigerwerte enthalten, die vordefinierte e/a-Dateizeiger *Stdin*, *"stdout"*, oder *"stderr"*.

Der Konstruktor zwei Parametern erstellt eine `CStdioFile` Objekt aus, und öffnet die entsprechende Datei mit dem angegebenen Pfad.

Wenn Sie NULL für beide übergeben *pOpenStream* oder *LpszFileName*, löst der Konstruktor eine `CInvalidArgException*`.

Wenn die Datei geöffnet oder erstellt werden kann nicht, löst der Konstruktor eine `CFileException*`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>  CStdioFile::m_pStream

Die `m_pStream` -Datenmember ist der Zeiger auf eine geöffnete Datei von der C-Laufzeitfunktion zurückgegeben `fopen`.

```
FILE* m_pStream;
```

### <a name="remarks"></a>Hinweise

Es ist NULL, wenn die Datei nicht geöffnet wurde oder geschlossen wurde.

##  <a name="open"></a>  CStdioFile::Open

Überladen. Öffnen Sie für die Verwendung mit der standardmäßigen vorgesehen `CStdioFile` Konstruktor.

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
Gemeinsame Nutzung und Zugriffsmodus. Gibt die Aktion an, der beim Öffnen der Datei an. Sie können Optionen kombinieren, mit dem bitweisen OR-(&#124;) Operator. Ein zugriffsberechtigungseintrag und ein Freigabe-Option sind erforderlich. die Modi ModeCreate und ModeNoInherit sind optional.

*pError*<br/>
Ein Zeiger auf eine vorhandene Datei-Ausnahmeobjekt, das den Status eines fehlgeschlagenen Vorgangs empfangen wird.

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

##  <a name="readstring"></a>  CStdioFile::ReadString

Liest Textdaten in einen Puffer, bis zu einem Höchstwert von *nmax*-1-Zeichen, aus der Datei zugeordneten der `CStdioFile` Objekt.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
Gibt einen Zeiger zu einem Benutzer bereitgestellten Puffer, der eine Null-terminierte Zeichenfolge empfangen wird.

*nMax*<br/>
Gibt an, dass die maximale Anzahl von Zeichen zu lesen, das abschließende Null-Zeichen wird dabei nicht mitgezählt.

*rString*<br/>
Ein Verweis auf eine `CString` -Objekt, das die Zeichenfolge enthalten soll, wenn die Funktion zurückgibt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Puffer, die die Textdaten enthält. NULL, wenn-Dateiende erreicht wurde, ohne alle Daten zu lesen. oder wenn Boolesch, FALSE, wenn das Ende der Datei erreicht wurde, ohne alle Daten zu lesen.

### <a name="remarks"></a>Hinweise

Lesen, wird durch das erste neue Zeilenumbruchzeichen beendet. Wenn in diesem Fall, weniger als *nmax*-1 Zeichen gelesen wurden, ein neue Zeilenumbruchzeichen im Puffer gespeichert ist. Ein Null-Zeichen ('\0') wird in beiden Fällen angefügt.

[CFile:: Read](../../mfc/reference/cfile-class.md#read) steht auch für Textmodus-Eingabe, aber es wird ein Carriage Return-Zeilenvorschub-Paar nicht beendet.

> [!NOTE]
>  Die `CString` Version dieser Funktion entfernt die `'\n'` falls vorhanden, jedoch nicht die Version LPTSTR.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>  CStdioFile::Seek

Positioniert den Zeiger in einer bereits geöffneten Datei.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Parameter

*lOff*<br/>
Die Anzahl der Bytes, die den Zeiger bewegen.

*nFrom*<br/>
Zeiger verschieben-Modus. Dabei muss es sich um einen der folgenden Werte sein:

- `CFile::begin`: Verschieben den Dateizeiger *lOff* Bytes vom Anfang der Datei weiterleiten.

- `CFile::current`: Verschieben den Dateizeiger *lOff* Bytes aus der aktuellen Position in der Datei.

- `CFile::end`: Verschieben den Dateizeiger *lOff* Byte vom Ende der Datei. Beachten Sie, dass *lOff* müssen werden Negative, Suchen in die vorhandene Datei; positive Werte werden nach dem Ende der Datei zu suchen.

### <a name="return-value"></a>Rückgabewert

Wenn die angeforderte Position rechtliche `Seek` gibt das neue Offset in Bytes vom Anfang der Datei zurück. Andernfalls ist der Rückgabewert nicht definiert und eine `CFileException` Objekt ausgelöst wird.

### <a name="remarks"></a>Hinweise

Die `Seek` Funktion ermöglicht zufälligen Zugriff auf Inhalts einer Datei durch den Zeiger bewegen einen angegebenen Betrag absolut oder relativ. Bei der Suche keine Daten tatsächlich gelesen. Ist die angeforderte Position größer als die Größe der Datei, die Dateilänge erweitert, um diese Position, und es wird keine Ausnahme ausgelöst werden.

Wenn eine Datei geöffnet wird, wird der Dateizeiger am Offset 0 (null) den Anfang der Datei positioniert.

Diese Implementierung der `Seek` basiert auf der Run-Time-Laufzeitbibliothek (CRT)-Funktion `fseek`. Es gibt einige Beschränkungen für die Verwendung von `Seek` auf im Textmodus geöffnete Streams. Weitere Informationen finden Sie unter [Fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie mit `Seek` zum Verschieben des Cursors 1000 Bytes vom Anfang der `cfile` Datei. Beachten Sie, dass `Seek` Daten werden nicht gelesen werden, damit Sie später aufrufen müssen [CStdioFile::ReadString](#readstring) zum Lesen von Daten.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>  CStdioFile::WriteString

Schreibt Daten aus einem Puffer in die zugeordnete Datei die `CStdioFile` Objekt.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
Gibt einen Zeiger auf einen Puffer, der eine Null-terminierte Zeichenfolge enthält.

### <a name="remarks"></a>Hinweise

Das abschließende Nullzeichen ( `\0`) nicht in die Datei geschrieben. Diese Methode schreibt neue Zeilenumbruchzeichen *Lpsz* mit der Datei als ein Paar aus Wagenrücklauf/Zeilenvorschub.

Wenn Sie möchten zum Schreiben von Daten, die nicht in eine Datei, die mit Null-terminiert ist `CStdioFile::Write` oder [CFile::Write](../../mfc/reference/cfile-class.md#write).

Diese Methode löst eine `CInvalidArgException*` bei Angabe von NULL für den *Lpsz* Parameter.

Diese Methode löst eine `CFileException*` als Reaktion auf Fehler im Dateisystem.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)
