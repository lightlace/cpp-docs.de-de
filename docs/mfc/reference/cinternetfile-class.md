---
title: CInternetFile Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1e4b05e2aceb8fb4c8a4abed0dd6038fff6cfee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CInternetFile::Abort](#abort)|Schließt die Datei, die alle Warnungen und Fehler ignorieren.|  
|[CInternetFile::Close](#close)|Schließt eine `CInternetFile` und seine Ressourcen freigegeben werden.|  
|[CInternetFile::Flush](#flush)|Leert den Inhalt von den Schreibpuffer und stellt sicher, dass die Daten im Arbeitsspeicher auf den Zielcomputer geschrieben werden.|  
|[CInternetFile::GetLength](#getlength)|Gibt die Größe der Datei zurück.|  
|[CInternetFile:: Read](#read)|Liest die Anzahl der angegebenen Bytes.|  
|[CInternetFile::ReadString](#readstring)|Liest einen Datenstrom von Zeichen.|  
|[CInternetFile::Seek](#seek)|Verschiebt den Zeiger in eine geöffnete Datei.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Legt fest, dass die Größe des Puffers, in denen Daten gelesen werden.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Legt fest, dass die Größe des Puffers, in dem Daten geschrieben werden.|  
|[CInternetFile:: Write](#write)|Schreibt die Anzahl der angegebenen Bytes.|  
|[CInternetFile::WriteString](#writestring)|Schreibt eine Null-terminierte Zeichenfolge in eine Datei.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Einen Typumwandlungsoperator für ein Internet-Handle.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|Ein Handle für eine Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Stellt eine Basisklasse für die [CHttpFile](../../mfc/reference/chttpfile-class.md) und [CGopherFile](../../mfc/reference/cgopherfile-class.md) Klassen der Datei. Erstellen Sie nie eine `CInternetFile` -Objekts direkt. Erstellen Sie ein Objekt von einer ihrer abgeleiteten Klassen stattdessen durch den Aufruf [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Sie können auch erstellen eine `CInternetFile` Objekt durch Aufrufen von [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 Die `CInternetFile` Memberfunktionen **öffnen**, `LockRange`, `UnlockRange`, und `Duplicate` nicht implementiert werden `CInternetFile`. Wenn Sie für diese Funktionen aufrufen einer `CInternetFile` -Objekt erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Erfahren Sie mehr darüber, wie `CInternetFile` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="abort"></a>CInternetFile::Abort  
 Schließt die Datei, die diesem Objekt zugeordnet, und die Datei nicht zum Lesen oder Schreiben verfügbar macht.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Datei nicht vor dem Löschen des Objekts geschlossen haben, wird es von der Destruktor geschlossen.  
  
 Beim Verarbeiten von Ausnahmen, **Abort** unterscheidet sich von [schließen](#close) in zwei wichtigen Aspekten. Zunächst wird die **Abort** Funktion löst keine Ausnahme auf Fehler, da sie Fehler ignoriert. Zweitens **Abort** nicht **ASSERT** Wenn die Datei nicht geöffnet wurde oder wurde bereits geschlossen.  
  
##  <a name="cinternetfile"></a>CInternetFile::CInternetFile  
 Diese Memberfunktion wird aufgerufen, wenn ein `CInternetFile` Objekt erstellt wird.  
  
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
 `hFile`  
 Ein Handle für eine Internetdatei.  
  
 `pstrFileName`  
 Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält.  
  
 `pConnection`  
 Ein Zeiger auf eine [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) Objekt.  
  
 *bReadMode*  
 Gibt an, ob die Datei schreibgeschützt ist.  
  
 `hSession`  
 Ein Handle für eine Internet-Sitzung.  
  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Servers.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CInternetFile` Objekt. Finden Sie unter [WinInet-Grundlagen](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CInternetFile` -Objekts direkt. Erstellen Sie ein Objekt von einer ihrer abgeleiteten Klassen stattdessen durch den Aufruf [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Sie können auch erstellen eine `CInternetFile` Objekt durch Aufrufen von [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="close"></a>CInternetFile::Close  
 Schließt eine `CInternetFile` und ihre Ressourcen freigegeben.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Datei zum Schreiben geöffnet wurde, wird es ein impliziter Aufruf [leeren](#flush) sichergestellt, dass alle Daten gepuffert wird an den Host geschrieben. Rufen Sie **schließen** Sie abschließend mithilfe einer Datei.  
  
##  <a name="flush"></a>CInternetFile::Flush  
 Rufen Sie diese Memberfunktion um den Inhalt von den Schreibpuffer zu leeren.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `Flush` sichergestellt, dass alle Daten im Arbeitsspeicher tatsächlich an den Zielcomputer geschrieben wurden und zum sicherstellen die Transaktion mit dem Hostcomputer wurde abgeschlossen. `Flush`gilt nur für `CInternetFile` Objekte zum Schreiben geöffnet.  
  
##  <a name="getlength"></a>CInternetFile::GetLength  
 Gibt die Größe der Datei zurück.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>CInternetFile::m_hFile  
 Ein Handle für die Datei, die diesem Objekt zugeordnet.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>CInternetFile::operator HINTERNET  
 Verwenden Sie diesen Operator, um das Windows-Handle für die aktuelle Sitzung mit Internet abzurufen.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>CInternetFile:: Read  
 Rufen Sie diese Memberfunktion auf, um im angegebenen Speicher zu lesen, beginnend mit `lpvBuf`, die angegebene Anzahl von Bytes, `nCount`.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf eine Speicheradresse, auf der Dateidaten gelesen werden.  
  
 `nCount`  
 Die Anzahl der zu schreibenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in den Puffer übertrageben Bytes. Der Rückgabewert ist möglicherweise kleiner als `nCount`, wenn das Ende der Datei erreicht wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt die Anzahl der tatsächlich gelesenen Bytes zurück – eine Zahl, die kleiner als `nCount` sein kann, wenn die Datei endet. Wenn beim Lesen der Datei werden ein Fehler auftritt, löst die Funktion eine [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt. Beachten Sie, dass der Lesevorgang nach dem Ende der Datei nicht als Fehler angesehen und keine Ausnahme ausgelöst wird.  
  
 Um sicherzustellen, dass alle Daten abgerufen wird, muss eine Anwendung aufrufen, weiterhin die **CInternetFile:: Read** Methode, bis die Methode NULL zurückgibt.  
  
##  <a name="readstring"></a>CInternetFile::ReadString  
 Rufen Sie diese Memberfunktion um zeichendatenstrom zu lesen, bis ein neue Zeilenumbruchzeichen gefunden wird.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Ein Zeiger auf eine Zeichenfolge, die die gelesene Zeile erhält.  
  
 `nMax`  
 Die maximale Anzahl der zu lesenden Zeichen.  
  
 `rString`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die gelesene Zeile empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Puffer mit einfachen aus abgerufenen Daten der [CInternetFile](../../mfc/reference/cinternetfile-class.md) Objekt. Unabhängig vom Datentyp des übergebenen Puffers an diese Methode, alle Manipulationen der Daten (z. B. die Konvertierung in Unicode) wird nicht ausgeführt, damit Sie die zurückgegebenen Daten auf die Struktur zuordnen, müssen Sie davon ausgehen, dass als wäre die **"void"\***  Typ zurückgegeben wurden.  
  
 **NULL** Ende der Datei erreicht wurde, ohne Lesen von Daten; oder, wenn boolean **"false"** Wenn Ende der Datei erreicht wurde, ohne alle Daten zu lesen.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion setzt die daraus resultierende Zeile in den Arbeitsspeicher, verweist der `pstr` Parameter. Er stoppt das Lesen von Zeichen bei Erreichen die maximale Anzahl von angegebenen Zeichen `nMax`. Der Puffer erhält immer ein abschließendes Nullzeichen an.  
  
 Beim Aufrufen `ReadString` erst nach Aufrufen von [SetReadBufferSize](#setreadbuffersize), erhalten Sie einen Puffer von 4096 Bytes.  
  
##  <a name="seek"></a>CInternetFile::Seek  
 Rufen Sie diese Memberfunktion um den Zeiger in einer zuvor geöffneten Datei neu zu positionieren.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Parameter  
 `lOffset`  
 Offset in Bytes, die den Lese-/Schreibzugriff Zeiger in der Datei zu verschieben.  
  
 `nFrom`  
 Relativer Verweis für den Offset. Dabei muss es sich um einen der folgenden Werte sein:  
  
- **CFile::begin** verschieben den Dateizeiger `lOff` Bytes vom Anfang der Datei weiterleiten.  
  
- **CFile::current** verschieben den Dateizeiger `lOff` Bytes aus der aktuellen Position in der Datei.  
  
- **CFile::end** verschieben den Dateizeiger `lOff` Bytes aus dem Ende der Datei. `lOff`muss negativ ist, in die vorhandene Datei zu suchen; positive Werte werden nach dem Ende der Datei gesucht.  
  
### <a name="return-value"></a>Rückgabewert  
 Das neue Byte offset vom Anfang der Datei, wenn die angeforderte Position zulässig ist; Andernfalls wird der Wert nicht definiert und eine [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt ausgelöst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die `Seek` -Funktion ermöglicht wahlfreien Zugriff auf den Inhalt einer Datei durch den Mauszeiger über einen bestimmten Zeitraum, absolut oder relativ. Keine Daten werden tatsächlich während der Seek gelesen.  
  
 Zu diesem Zeitpunkt wird nur ein Aufruf von dieser Memberfunktion für die zugeordneten Daten unterstützt `CHttpFile` Objekte. Es ist nicht für FTP oder Gopher-Anforderungen unterstützt. Beim Aufrufen `Seek` für einen dieser Dienste nicht unterstützt, es übergibt wieder auf die Win32-Fehlercode **ERROR_INTERNET_INVALID_OPERATION**.  
  
 Wenn eine Datei geöffnet wird, wird der Dateizeiger am Offset 0 (null) den Anfang der Datei.  
  
> [!NOTE]
>  Mit `Seek` verursachen einen impliziten Aufruf [leeren](#flush).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die Implementierung der Basisklasse ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize  
 Rufen Sie diese Memberfunktion zum Festlegen der Größe des temporären read Puffers, in dem eine `CInternetFile`-abgeleitetes Objekt.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Parameter  
 *nReadSize*  
 Die gewünschte Puffergröße in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die zugrunde liegenden WinInet-APIs nicht Pufferung ausführen, wählen Sie eine Puffergröße, die Ihre Anwendung zum Lesen von Daten effizient pivotiert werden, unabhängig von der Menge der zu lesenden Daten erlaubt. Wenn Sie jeden Aufruf [lesen](#read) normalerweise umfasst eine große Aount von Daten (z. B. mindestens vier-Kilobyte), sollten Sie keinen Puffer benötigen. Allerdings beim Aufrufen **lesen** abzurufenden kleine Datenpakete, oder wenn Sie [ReadString](#readstring) , einzelne Zeilen zu einem Zeitpunkt, zu lesen, und klicken Sie dann ein Lesepuffer verbessert die Leistung der Anwendung.  
  
 Wird standardmäßig ein `CInternetFile` Objekt bietet keine Pufferung zum Lesen. Wenn Sie diese Memberfunktion aufrufen, müssen Sie Sie sicher sein, dass die Datei für den Lesezugriff geöffnet wurde.  
  
 Sie können die Größe des Puffers zu einem beliebigen Zeitpunkt erhöhen, aber Verkleinern des Puffers hat keine Auswirkungen. Beim Aufrufen [ReadString](#readstring) erst nach Aufrufen von `SetReadBufferSize`, erhalten Sie einen Puffer von 4096 Bytes.  
  
##  <a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize  
 Rufen Sie diese Memberfunktion zum Festlegen der Größe des Puffers temporäre schreiben, in dem eine `CInternetFile`-abgeleitetes Objekt.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Parameter  
 *nWriteSize*  
 Die Größe des Puffers in Byte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Wählen Sie das zugrunde liegende WinInet-APIs nicht Pufferung, führen Sie daher eine Puffergröße, die Ihre Anwendung Daten effizient unabhängig von der Menge der zu schreibenden Daten schreiben erlaubt. Wenn Sie jeden Aufruf [schreiben](#write) normalerweise umfasst eine große Menge von Daten (z. B. vier oder mehr Kilobyte zu einem Zeitpunkt), sollten Sie keinen Puffer benötigen. Allerdings beim Aufrufen [schreiben](#write) zum Schreiben von kleiner Segmenten der Daten ein Schreibpuffer verbessert die Leistung Ihrer Anwendung.  
  
 Wird standardmäßig ein `CInternetFile` Objekt bietet keine Pufferung zum Schreiben. Wenn Sie diese Memberfunktion aufrufen, müssen Sie Sie sicher sein, dass die Datei für Schreibzugriff geöffnet wurde. Sie können die Größe des den Schreibpuffer jederzeit ändern, aber diesem Fall kommt es einen impliziten Aufruf [leeren](#flush).  
  
##  <a name="write"></a>CInternetFile:: Write  
 Rufen Sie diese Memberfunktion im angegebenen Speicher schreiben `lpvBuf`, wird die angegebene Anzahl von Bytes, `nCount`.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf das erste Byte geschrieben werden.  
  
 `nCount`  
 Gibt die Anzahl der zu schreibenden Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Fehler, beim Schreiben der Daten auftritt, löst die Funktion eine [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt.  
  
##  <a name="writestring"></a>CInternetFile::WriteString  
 Diese Funktion schreibt eine Null-terminierte Zeichenfolge zur zugehörigen Datei.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Ein Zeiger auf eine Zeichenfolge mit dem Inhalt geschrieben werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Fehler, beim Schreiben der Daten auftritt, löst die Funktion eine [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt.  
  
## <a name="see-also"></a>Siehe auch  
 [CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)
