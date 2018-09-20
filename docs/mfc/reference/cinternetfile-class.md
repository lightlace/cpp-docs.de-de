---
title: CInternetFile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b28cfffbe3ce8304d12f5a52cd3cf3af7b6679c2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406853"
---
# <a name="cinternetfile-class"></a>CInternetFile-Klasse

Ermöglicht den Zugriff auf Dateien auf Remotesystemen, die Internetprotokolle verwenden.

## <a name="syntax"></a>Syntax

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile::CInternetFile](#cinternetfile)|Erstellt ein `CInternetFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile::Abort](#abort)|Schließt die Datei, ignorieren alle Warnungen und Fehler.|
|[CInternetFile::Close](#close)|Schließt eine `CInternetFile` und gibt seine Ressourcen frei.|
|[CInternetFile::Flush](#flush)|Leert den Schreibpuffer den Inhalt, und stellt sicher, dass die Daten im Arbeitsspeicher auf den Zielcomputer geschrieben werden.|
|[CInternetFile::GetLength](#getlength)|Gibt die Größe der Datei zurück.|
|[CInternetFile:: Read](#read)|Liest die Anzahl der angegebenen Bytes.|
|[CInternetFile::ReadString](#readstring)|Liest einen Datenstrom von Zeichen.|
|[CInternetFile::Seek](#seek)|Positioniert den Zeiger in einer geöffneten Datei.|
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Legt fest, dass die Größe des Puffers, in dem Daten gelesen werden.|
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Legt fest, dass die Größe des Puffers, in dem Daten geschrieben werden.|
|[CInternetFile:: Write](#write)|Schreibt die Anzahl der angegebenen Bytes.|
|[CInternetFile::WriteString](#writestring)|Schreibt eine Null-terminierte Zeichenfolge in eine Datei an.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Ein Umwandlungsoperator für ein Internet-Handle.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CInternetFile::m_hFile](#m_hfile)|Ein Handle für eine Datei.|

## <a name="remarks"></a>Hinweise

Stellt eine Basisklasse für die [CHttpFile](../../mfc/reference/chttpfile-class.md) und [CGopherFile](../../mfc/reference/cgopherfile-class.md) Datei Klassen. Erstellen Sie nie eine `CInternetFile` direkt. Erstellen Sie stattdessen ein Objekt eines abgeleiteten Klassen, durch den Aufruf [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Sie können auch erstellen eine `CInternetFile` Objekt durch Aufrufen von [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

Die `CInternetFile` Memberfunktionen `Open`, `LockRange`, `UnlockRange`, und `Duplicate` sind nicht für implementiert `CInternetFile`. Wenn Sie für diese Funktionen aufrufen einer `CInternetFile` Objekt ist, erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Weitere Informationen finden Sie `CInternetFile` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="abort"></a>  CInternetFile::Abort

Schließt die Datei, die diesem Objekt zugeordnet, und ist die Datei zum Lesen oder Schreiben nicht verfügbar.

```
virtual void Abort();
```

### <a name="remarks"></a>Hinweise

Wenn Sie vor dem Zerstören des Objekts nicht die Datei geschlossen haben, wird Sie von der Destruktor für Sie geschlossen.

Bei der Behandlung von Ausnahmen, `Abort` unterscheidet sich von [schließen](#close) in zwei wichtigen Punkten. Zunächst wird die `Abort` Funktion löst keine Ausnahme bei Fehlern, weil es Fehler ignoriert. Zweitens `Abort` nicht **ASSERT** sollte diese Datei nicht geöffnet wurde oder wurde bereits geschlossen.

##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile

Diese Memberfunktion wird aufgerufen, wenn eine `CInternetFile` Objekt erstellt wird.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);


CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>Parameter

*hFile*<br/>
Ein Handle für eine Internetdatei.

*pstrFileName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält.

*pConnection*<br/>
Ein Zeiger auf eine [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) Objekt.

*bReadMode*<br/>
Gibt an, ob die Datei schreibgeschützt ist.

*hSession*<br/>
Ein Handle für eine internetsitzung.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Servers.

*dwContext*<br/>
Der Kontextbezeichner für den `CInternetFile` Objekt. Finden Sie unter [WinInet-Grundlagen](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

### <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CInternetFile` direkt. Erstellen Sie stattdessen ein Objekt eines abgeleiteten Klassen, durch den Aufruf [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Sie können auch erstellen eine `CInternetFile` Objekt durch Aufrufen von [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

##  <a name="close"></a>  CInternetFile::Close

Schließt eine `CInternetFile` und gibt seine Ressourcen frei.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Wenn die Datei zum Schreiben geöffnet wurde, besteht ein implizites Aufrufs von [leeren](#flush) um sicherzustellen, dass alle Daten gepuffert werden an den Host geschrieben. Rufen Sie `Close` Sie abschließend mithilfe einer Datei.

##  <a name="flush"></a>  CInternetFile::Flush

Rufen Sie diese Memberfunktion um den Inhalt von den Schreibpuffer zu leeren.

```
virtual void Flush();
```

### <a name="remarks"></a>Hinweise

Verwendung `Flush` um sicherzustellen, dass alle Daten im Speicher tatsächlich auf den Zielcomputer geschrieben wurden und um sicherzustellen, die Transaktion mit dem Host-Computer abgeschlossen wurde. `Flush` gilt nur für `CInternetFile` Objekte, die zum Schreiben geöffnet.

##  <a name="getlength"></a>  CInternetFile::GetLength

Gibt die Größe der Datei zurück.

```
virtual ULONGLONG GetLength() const;
```

##  <a name="m_hfile"></a>  CInternetFile::m_hFile

Ein Handle für die Datei, die diesem Objekt zugeordnet.

```
HINTERNET m_hFile;
```

##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET

Verwenden Sie diesen Operator, um das Windows-Handle für die aktuelle Sitzung von Internet abzurufen.

```
operator HINTERNET() const;
```

##  <a name="read"></a>  CInternetFile:: Read

Rufen Sie diese Memberfunktion zum Lesen im angegebenen Speicher, beginnend bei *LpvBuf*, wird die angegebene Anzahl von Bytes, *nCount*.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger auf eine Speicheradresse, auf der Dateidaten gelesen werden.

*nCount*<br/>
Die Anzahl der zu schreibenden Bytes.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der in den Puffer übertrageben Bytes. Der Rückgabewert ist möglicherweise kleiner als *nCount* Wenn am Ende der Datei erreicht wurde.

### <a name="remarks"></a>Hinweise

Die Funktion gibt die Anzahl der tatsächlich gelesenen Bytes zurück – eine Zahl, die möglicherweise weniger als *nCount* Wenn die Datei endet. Wenn beim Lesen der Datei ein Fehler auftritt, löst die Funktion eine [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt. Beachten Sie, dass der Lesevorgang nach dem Ende der Datei nicht als Fehler angesehen und keine Ausnahme ausgelöst wird.

Um sicherzustellen, dass alle Daten abgerufen werden, muss eine Anwendung aufrufen, weiterhin die `CInternetFile::Read` Methode, bis die Methode 0 (null) zurückgegeben.

##  <a name="readstring"></a>  CInternetFile::ReadString

Rufen Sie diese Memberfunktion, um einen Stream von Zeichen zu lesen, bis ein neue Zeilenumbruchzeichen gefunden.

```
virtual BOOL ReadString(CString& rString);


virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Parameter

*pStr*<br/>
Ein Zeiger auf eine Zeichenfolge, die erhält die Zeile, die gelesen wird.

*nmax.*<br/>
Die maximale Anzahl der zu lesenden Zeichen.

*rString*<br/>
Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, in der Zeile lesen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Puffer mit unformatierten Daten abgerufen, die von der [CInternetFile](../../mfc/reference/cinternetfile-class.md) Objekt. Unabhängig vom Datentyp des übergebenen Puffers an diese Methode, alle Manipulationen der Daten (z. B. die Konvertierung in Unicode) wird nicht ausgeführt, damit Sie die zurückgegebenen Daten auf die Struktur zuordnen, müssen Sie erwarten, als ob die **"void"** <strong>\*</strong> Typ zurückgegeben wurden.

NULL, wenn-Dateiende erreicht wurde, ohne alle Daten zu lesen. oder, wenn Boolesch, FALSE, wenn das Ende der Datei erreicht wurde, ohne alle Daten zu lesen.

### <a name="remarks"></a>Hinweise

Die Funktion wird die daraus resultierende Zeile in den Speicher der *Pstr* Parameter. Lesen von Zeichen beendet, wenn sie die maximale Anzahl der vom angegebenen Zeichen erreicht *nmax*. Der Puffer erhält immer ein abschließendes Nullzeichen an.

Wenn Sie aufrufen `ReadString` erst nach Aufrufen von [SetReadBufferSize](#setreadbuffersize), erhalten Sie einen Puffer von 4096 Bytes.

##  <a name="seek"></a>  CInternetFile::Seek

Rufen Sie diese Memberfunktion um den Zeiger in einer bereits geöffneten Datei neu zu positionieren.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Parameter

*lOffset*<br/>
Der Offset in Bytes, die den Zeiger für die Lese-/Schreibzugriff in der Datei zu verschieben.

*nWenn*<br/>
Relativer Verweis für den Offset. Dabei muss es sich um einen der folgenden Werte sein:

- `CFile::begin` Verschieben den Dateizeiger *lOff* Bytes vom Anfang der Datei weiterleiten.

- `CFile::current` Verschieben den Dateizeiger *lOff* Bytes aus der aktuellen Position in der Datei.

- `CFile::end` Verschieben den Dateizeiger *lOff* Byte vom Ende der Datei. *lOff* müssen werden Negative, Suchen in die vorhandene Datei; positive Werte werden nach dem Ende der Datei zu suchen.

### <a name="return-value"></a>Rückgabewert

Das neue Byteoffset vom Anfang der Datei, wenn die angeforderte Position gültig ist; Andernfalls wird der Wert nicht definiert und eine [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt ausgelöst wird.

### <a name="remarks"></a>Hinweise

Die `Seek` Funktion ermöglicht zufälligen Zugriff auf Inhalts einer Datei durch den Zeiger bewegen einen angegebenen Betrag absolut oder relativ. Bei der Suche keine Daten tatsächlich gelesen.

Zu diesem Zeitpunkt wird nur ein Aufruf dieser Memberfunktion für die zugeordneten Daten unterstützt `CHttpFile` Objekte. Es wird nicht für FTP oder Gopher-Anforderungen unterstützt. Wenn Sie aufrufen `Seek` für einen dieser Dienste nicht unterstützt, es übergibt wieder dem Win32-Fehlercode ERROR_INTERNET_INVALID_OPERATION.

Wenn eine Datei geöffnet wird, ist der Dateizeiger am Offset 0 (null) den Anfang der Datei ein.

> [!NOTE]
>  Mithilfe von `Seek` möglicherweise ein implizites Aufrufs von [leeren](#flush).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für die Implementierung der Basisklasse ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).

##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize

Rufen Sie diese Memberfunktion zum Festlegen der Größe des temporären Lesepuffers ein, die eine `CInternetFile`-abgeleitetes Objekt.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Parameter

*nReadSize*<br/>
Die gewünschte Puffergröße in Bytes.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Der zugrunde liegenden WinInet-APIs nicht ausführen, Pufferung, also wählen Sie eine Puffergröße, die Ihre Anwendung zum Lesen von Daten effizient, unabhängig von der Menge der zu lesenden Daten ermöglicht. Wenn Sie jeden Aufruf [lesen](#read) normalerweise umfasst eine große Aount von Daten (z. B. mindestens vier-Kilobyte), sollte Sie keinen Puffer erforderlich. Allerdings Aufrufen `Read` abzurufenden kleine Datenblöcke, oder wenn Sie [ReadString](#readstring) , einzelne Zeilen zu einem Zeitpunkt, zu lesen, und klicken Sie dann ein Lesepuffer verbessert die Leistung der Anwendung.

Standardmäßig eine `CInternetFile` Objekt bietet keine Pufferung für das Lesen. Wenn Sie diese Memberfunktion aufrufen, müssen Sie darauf achten, dass die Datei für den Lesezugriff geöffnet wurde.

Sie können die Größe des Puffers zu einem beliebigen Zeitpunkt erhöhen, aber beim Verkleinern des Puffers hat keine Auswirkungen. Wenn Sie aufrufen [ReadString](#readstring) erst nach Aufrufen von `SetReadBufferSize`, erhalten Sie einen Puffer von 4096 Bytes.

##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize

Rufen Sie diese Memberfunktion zum Festlegen der Größe der temporären schreiben Puffers, in einem `CInternetFile`-abgeleitetes Objekt.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Parameter

*nWriteSize*<br/>
Die Größe des Puffers in Byte.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Wählen Sie die zugrunde liegende WinInet-APIs führen Sie keine Pufferung, also eine Puffergröße, die Ihre Anwendung zum Schreiben von Daten effizient, unabhängig von die Menge der zu schreibenden Daten ermöglicht. Wenn Sie jeden Aufruf [schreiben](#write) normalerweise umfasst eine große Menge von Daten (z. B. vier oder mehr KB jeweils) kein Puffer erforderlich. Aber wenn Sie aufrufen [schreiben](#write) um kleine Datenblöcke zu schreiben, die ein Schreibpuffer verbessert die Leistung Ihrer Anwendung.

Standardmäßig eine `CInternetFile` Objekt bietet keine Pufferung zum Schreiben. Wenn Sie diese Memberfunktion aufrufen, müssen Sie darauf achten, dass die Datei für den Schreibzugriff geöffnet wurde. Sie können die Größe des Puffers schreiben zu einem beliebigen Zeitpunkt ändern, aber diesem Fall kommt es einen impliziten Aufruf [leeren](#flush).

##  <a name="write"></a>  CInternetFile:: Write

Rufen Sie diese Memberfunktion zum Schreiben im angegebenen Speicher, *LpvBuf*, wird die angegebene Anzahl von Bytes, *nCount*.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger auf das erste Byte geschrieben werden.

*nCount*<br/>
Gibt die Anzahl der zu schreibenden Bytes.

### <a name="remarks"></a>Hinweise

Wenn ein Fehler, beim Schreiben der Daten auftritt, löst die Funktion eine [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt, das den Fehler beschreibt.

##  <a name="writestring"></a>  CInternetFile::WriteString

Diese Funktion schreibt eine Null-terminierte Zeichenfolge in die zugehörige Datei.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Parameter

*pStr*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Inhalt geschrieben werden.

### <a name="remarks"></a>Hinweise

Wenn ein Fehler, beim Schreiben der Daten auftritt, löst die Funktion eine [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt, das den Fehler beschreibt.

## <a name="see-also"></a>Siehe auch

[CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)
