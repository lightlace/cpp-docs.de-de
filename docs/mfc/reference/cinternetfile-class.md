---
title: CInternetFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile class
- Internet files
- Internet files, CInternetFile class
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e1d6227ebd642025e6b00019518d29080cf0454
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetfile-class"></a>CInternetFile-Klasse
Ermöglicht den Zugriff auf Dateien auf Remotesystemen, die Internetprotokolle verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|Erstellt ein `CInternetFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|Schließt die Datei, die alle Warnungen und Fehler werden ignoriert.|  
|[CInternetFile::Close](#close)|Schließt eine `CInternetFile` und seine Ressourcen freigegeben werden.|  
|[CInternetFile::Flush](#flush)|Leert den Inhalt des Puffers schreiben und stellt sicher, dass die Daten im Arbeitsspeicher auf den Zielcomputer geschrieben werden.|  
|[CInternetFile::GetLength](#getlength)|Gibt die Größe der Datei zurück.|  
|[CInternetFile:: Read](#read)|Liest die Anzahl der angegebenen Bytes.|  
|[CInternetFile::ReadString](#readstring)|Liest einen Zeichenstream.|  
|[CInternetFile::Seek](#seek)|Verschiebt den Zeiger in eine geöffnete Datei.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Legt fest, dass die Größe des Puffers, in denen Daten gelesen werden.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Legt fest, dass die Größe des Puffers, in dem Daten geschrieben werden.|  
|[CInternetFile:: Write](#write)|Schreibt die Anzahl der angegebenen Bytes.|  
|[CInternetFile::WriteString](#writestring)|Schreibt eine Null-terminierte Zeichenfolge in eine Datei.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Ein Umwandlungsoperator für ein Internet-Handle.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|Ein Handle für eine Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Stellt eine Basisklasse für die [CHttpFile](../../mfc/reference/chttpfile-class.md) und [CGopherFile](../../mfc/reference/cgopherfile-class.md) Datei Klassen. Erstellen Sie nie eine `CInternetFile` direkt. Erstellen Sie stattdessen ein Objekt eines abgeleiteten Klassen durch Aufrufen von [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Sie können auch erstellen eine `CInternetFile` -Objekt durch Aufrufen von [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 Die `CInternetFile` Memberfunktionen **öffnen**, `LockRange`, `UnlockRange`, und `Duplicate` nicht implementiert sind `CInternetFile`. Wenn Sie diese Funktionen aufrufen, die sich auf eine `CInternetFile` -Objekt erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Weitere Informationen zur Verwendung `CInternetFile` arbeitet mit den anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="abort"></a>CInternetFile::Abort  
 Schließt die Datei, die diesem Objekt zugeordnet und wird die Datei zum Lesen oder Schreiben nicht verfügbar.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Datei nicht vor dem Löschen des Objekts geschlossen haben, wird es von der Destruktor geschlossen.  
  
 Beim Verarbeiten von Ausnahmen, **Abort** unterscheidet sich von [schließen](#close) in zwei wichtigen Aspekten. Zuerst wird die **Abort** Funktion löst keine Ausnahme bei Fehlern, weil er Fehler ignoriert. Zweitens **Abort** nicht **ASSERT** Datei wurde nicht geöffnet oder wurde bereits geschlossen.  
  
##  <a name="cinternetfile"></a>CInternetFile::CInternetFile  
 Diese Member-Funktion wird aufgerufen, wenn ein `CInternetFile` Objekt erstellt wird.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CInternetFile` Objekt. Finden Sie unter [WinInet-Grundlagen](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CInternetFile` direkt. Erstellen Sie stattdessen ein Objekt eines abgeleiteten Klassen durch Aufrufen von [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Sie können auch erstellen eine `CInternetFile` -Objekt durch Aufrufen von [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="close"></a>CInternetFile::Close  
 Schließt eine `CInternetFile` und ihre Ressourcen frei.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Datei zum Schreiben geöffnet wurde, wird es ein impliziter Aufruf [leeren](#flush) um sicherzustellen, dass alle Daten gepuffert, bezieht sich auf dem Host. Rufen Sie **schließen** Sie abschließend mithilfe einer Datei.  
  
##  <a name="flush"></a>CInternetFile::Flush  
 Rufen Sie diese Memberfunktion, um den Inhalt des Puffers schreiben zu leeren.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `Flush` um sicherzustellen, dass alle Daten im Speicher tatsächlich auf den Zielcomputer geschrieben wurden und um zu gewährleisten, die Transaktion mit dem Host-Computer abgeschlossen wurde. `Flush`gilt nur für `CInternetFile` Objekte zum Schreiben geöffnet.  
  
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
 Die Funktion gibt die Anzahl der tatsächlich gelesenen Bytes zurück – eine Zahl, die kleiner als `nCount` sein kann, wenn die Datei endet. Tritt ein Fehler beim Lesen der Datei, löst die Funktion einer [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt. Beachten Sie, dass der Lesevorgang nach dem Ende der Datei nicht als Fehler angesehen und keine Ausnahme ausgelöst wird.  
  
 Um sicherzustellen, dass alle Daten abgerufen wird, muss eine Anwendung aufrufen, weiterhin die **CInternetFile:: Read** Methode, bis die Methode gibt&0; (null) zurück.  
  
##  <a name="readstring"></a>CInternetFile::ReadString  
 Rufen Sie diese Memberfunktion, um einen Stream von Zeichen gelesen, bis ein neue Zeilenumbruchzeichen gefunden wird.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Ein Zeiger auf eine Zeichenfolge, die erhält die Zeile gelesen wird.  
  
 `nMax`  
 Die maximale Anzahl der zu lesenden Zeichen.  
  
 `rString`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das die gelesene Zeile empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Puffer mit einfachen Daten aus der [CInternetFile](../../mfc/reference/cinternetfile-class.md) Objekt. Unabhängig vom Datentyp des übergebenen Puffers an diese Methode, alle Manipulationen der Daten (z. B. die Konvertierung in Unicode) wird nicht ausgeführt, damit Sie die Struktur die zurückgegebenen Daten zuordnen müssen Sie erwarten, als ob die **void\* ** Typ zurückgegeben wurden.  
  
 **NULL** Ende der Datei erreicht wurde, ohne alle Daten lesen oder, wenn boolean **FALSE** Wenn das Ende der Datei erreicht wurde, ohne alle Daten zu lesen.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion wird die resultierende Linie in den Speicher der `pstr` Parameter. Er stoppt das Lesen von Zeichen bei Erreichen die maximale Anzahl von angegebenen Zeichen `nMax`. Der Puffer empfängt immer ein abschließendes Nullzeichen.  
  
 Wenn Sie aufrufen `ReadString` erst nach Aufrufen von [SetReadBufferSize](#setreadbuffersize), erhalten Sie einen Puffer von 4096 Bytes.  
  
##  <a name="seek"></a>CInternetFile::Seek  
 Rufen Sie diese Memberfunktion um den Zeiger in einer bereits geöffneten Datei neu zu positionieren.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Parameter  
 `lOffset`  
 Offset in Bytes, die den Lese-Schreib-Zeiger in der Datei zu verschieben.  
  
 `nFrom`  
 Relativer Verweis für den Offset. Dabei muss es sich um einen der folgenden Werte sein:  
  
- **CFile::begin** den Dateizeiger verschoben `lOff` Bytes vom Anfang der Datei weitergeleitet.  
  
- **CFile::current** den Dateizeiger verschoben `lOff` Bytes aus der aktuellen Position in der Datei.  
  
- **CFile::end** den Dateizeiger verschoben `lOff` Bytes vom Ende der Datei. `lOff`muss negativ, Suchen in die vorhandene Datei sein. positive Werte werden nach dem Ende der Datei suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das neue Byte offset vom Anfang der Datei, wenn die angeforderte Position zulässig ist; Andernfalls wird der Wert nicht definiert und ein [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt ausgelöst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die `Seek` Funktion ermöglicht den wahlfreien Zugriff auf den Inhalt einer Datei durch Bewegen des Mauszeigers einen angegebenen Betrag, absolut oder relativ. Während der Suche ist keine Daten gelesen.  
  
 Zu diesem Zeitpunkt wird nur ein Aufruf von dieser Memberfunktion für die zugeordneten Daten unterstützt `CHttpFile` Objekte. Es wird nicht für FTP oder Gopher-Anfragen unterstützt. Wenn Sie aufrufen `Seek` für eine der folgenden nicht unterstützten Diensten, er übergibt zurück auf den Win32-Fehlercode **ERROR_INTERNET_INVALID_OPERATION**.  
  
 Wenn eine Datei geöffnet wird, wird der Dateizeiger am Offset 0 ist, am Anfang der Datei.  
  
> [!NOTE]
>  Mithilfe von `Seek` verursachen einen impliziten Aufruf [leeren](#flush).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die Implementierung der Basisklasse ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize  
 Rufen Sie diese Memberfunktion zum Festlegen der Größe des temporären schreibgeschützten Puffers durch ein `CInternetFile`-abgeleitetes Objekt.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Parameter  
 *nReadSize*  
 Die gewünschte Puffergröße in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die zugrunde liegende WinInet-APIs nicht Pufferung ausführen, wählen Sie also eine Puffergröße, die Daten effizient, unabhängig von der Menge der zu lesenden Daten gelesen werden können. Wenn jeder Aufruf [lesen](#read) normalerweise umfasst eine große Aount von Daten (z. B. mindestens vier Kilobyte), sollte Sie keinen Puffer erforderlich. Jedoch wenn Sie aufrufen **lesen** abzurufenden kleine Datenblöcke, oder wenn Sie [ReadString](#readstring) einzelne Zeilen zu einem Zeitpunkt zu lesen, und klicken Sie dann ein Lesepuffer verbessert die Leistung der Anwendung.  
  
 In der Standardeinstellung ein `CInternetFile` Objekt bietet kein Pufferung zum Lesen. Wenn Sie diese Memberfunktion aufrufen, müssen Sie sicher sein, dass die Datei für den Lesezugriff geöffnet wurde.  
  
 Sie können die Größe des Puffers zu einem beliebigen Zeitpunkt erhöhen, aber Verkleinern des Puffers hat keine Auswirkung. Wenn Sie aufrufen [ReadString](#readstring) erst nach Aufrufen von `SetReadBufferSize`, erhalten Sie einen Puffer von 4096 Bytes.  
  
##  <a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize  
 Rufen Sie diese Memberfunktion zum Festlegen der Größe des Puffers temporäre schreiben, eine `CInternetFile`-abgeleitetes Objekt.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Parameter  
 *nWriteSize*  
 Die Größe des Puffers in Byte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Wählen Sie die zugrunde liegende WinInet-APIs führen Sie keine Pufferung, also eine Puffergröße, die Daten effizient unabhängig von der Menge der zu schreibenden Daten geschrieben werden können. Wenn Sie jeden Aufruf [schreiben](#write) normalerweise umfasst eine große Menge von Daten (z. B. vier oder mehr KB jeweils), sollte Sie keinen Puffer erforderlich. Aber wenn Sie aufrufen [schreiben](#write) zum Schreiben von kleiner Datensegmenten ein Schreibpuffer verbessert die Leistung der Anwendung.  
  
 In der Standardeinstellung ein `CInternetFile` Objekt bietet kein Pufferung zum Schreiben. Wenn Sie diese Memberfunktion aufrufen, müssen Sie sicher sein, dass die Datei für Schreibzugriff geöffnet wurde. Sie können die Größe des Puffers schreiben jederzeit ändern, aber diesem Fall kommt es einen impliziten Aufruf [leeren](#flush).  
  
##  <a name="write"></a>CInternetFile:: Write  
 Rufen Sie diese Memberfunktion zum Schreiben in den angegebenen Speicher, `lpvBuf`, wird die angegebene Anzahl von Bytes, `nCount`.  
  
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
 Wenn beim Schreiben der Daten wurde ein Fehler auftreten, löst die Funktion einer [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt.  
  
##  <a name="writestring"></a>CInternetFile::WriteString  
 Diese Funktion schreibt eine Null-terminierte Zeichenfolge in die zugehörige Datei.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Ein Zeiger auf eine Zeichenfolge mit dem Inhalt geschrieben werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn beim Schreiben der Daten wurde ein Fehler auftreten, löst die Funktion einer [CInternetException](../../mfc/reference/cinternetexception-class.md) -Objekt, das den Fehler beschreibt.  
  
## <a name="see-also"></a>Siehe auch  
 [CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)

