---
title: CStdioFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile class
- I/O [MFC], stream
- stream I/O
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
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
ms.openlocfilehash: f3f036b409067676fdf12db9751cac1ea8025140
ms.lasthandoff: 02/24/2017

---
# <a name="cstdiofile-class"></a>CStdioFile-Klasse
C-Laufzeit-Stream-Datei darstellt, da von der Funktion zur Laufzeit [Fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|Erstellt ein `CStdioFile` Objekt von einem Zeiger Pfad- oder Dateiname.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|Überladen. Open dient zur Verwendung mit der standardmäßigen `CStdioFile` Konstruktor (überschreibt [CFile::Open](../../mfc/reference/cfile-class.md#open)).|  
|[CStdioFile::ReadString](#readstring)|Liest eine Textzeile an.|  
|[CStdioFile::Seek](#seek)|Positioniert den Zeiger auf den aktuellen Datei.|  
|[CStdioFile::WriteString](#writestring)|Schreibt eine einzelne Textzeile.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|Enthält einen Zeiger auf eine geöffnete Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Stream-Dateien werden gepuffert und im Textmodus (Standard) oder Binärmodus geöffnet werden können.  
  
 Text-Modus bietet speziellen Verarbeitung für Wagenrücklauf-Zeilenvorschub-Paare. Beim Schreiben eines Zeilenvorschubs (0x0A) in einen Text-Modus Zeichen `CStdioFile` -Objekt, das Paar Byte (0x0D, 0x0A) wird gesendet, um die Datei. Wenn Sie lesen, das Paar Byte (0x0D, 0x0A) wird auf ein einzelnes 0x0A Byte übersetzt.  
  
 Die [CFile](../../mfc/reference/cfile-class.md) Funktionen [doppelte](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), und [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) können nicht für `CStdioFile`.  
  
 Wenn Sie diese Funktionen aufrufen, die sich auf eine `CStdioFile`, erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Weitere Informationen zur Verwendung von `CStdioFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cstdiofile"></a>CStdioFile::CStdioFile  
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
 `pOpenStream`  
 Gibt den Dateizeiger zurückgegeben, die durch einen Aufruf der C-Laufzeitfunktion [Fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 `lpszFileName`  
 Gibt eine Zeichenfolge, die den Pfad zur gewünschten Datei. Der Pfad kann relativ oder absolut sein.  
  
 `nOpenFlags`  
 Gibt Optionen für die Erstellung, Freigabe von Dateien und Zugriffsmodi für die Datei. Sie können mehrere Optionen angeben, mit dem bitweisen OR ( `|`) Operator.  
  
 Ein ist Datei-Modus erforderlich; andere Modi sind optional. Finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) eine Liste der Optionen und andere Flags. In MFC, Version 3.0 und höher sind die Freigabe Flags zulässig.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor wird nicht Anfügen einer Datei an die `CStdioFile` Objekt. Wenn Sie diesen Konstruktor verwenden, müssen Sie mithilfe der `CStdioFile::Open` Methode, um eine Datei öffnen, und fügen Sie es auf die `CStdioFile` Objekt.  
  
 Der Konstruktor für die einzelnen Parameter fügt zu eine geöffneten Datei-Stream der `CStdioFile` Objekt. Zulässige Zeigerwerte sind die vordefinierten Eingabe/Ausgabe-Dateizeiger `stdin`, `stdout`, oder `stderr`.  
  
 Der Konstruktor zwei Parameter erstellt ein `CStdioFile` -Objekt und öffnet die entsprechende Datei mit dem angegebenen Pfad.  
  
 Wenn Sie übergeben `NULL` für beide `pOpenStream` oder `lpszFileName`, löst der Konstruktor eine `CInvalidArgException*`.  
  
 Wenn die Datei geöffnet oder erstellt werden kann nicht, löst der Konstruktor eine `CFileException*`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#37;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="m_pstream"></a>CStdioFile::m_pStream  
 Die `m_pStream` -Datenmember ist der Zeiger auf eine geöffnete Datei von der C-Laufzeitfunktion zurückgegeben `fopen`.  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist **NULL** Datei wurde noch nie geöffnet oder geschlossen wurde.  
  
##  <a name="open"></a>CStdioFile::Open  
 Überladen. Open dient zur Verwendung mit der standardmäßigen `CStdioFile` Konstruktor.  
  
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
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zur gewünschten Datei. Der Pfad kann relativ oder absolut sein.  
  
 `nOpenFlags`  
 Gemeinsame Nutzung und Zugriffsmodus. Gibt die Aktion an, die beim Öffnen der Datei. Sie können Optionen kombinieren, mit dem Operator bitweises OR (|). Eine Access-Berechtigung und eine Freigabe-Option ist erforderlich. die Modi ModeCreate und ModeNoInherit sind optional.  
  
 `pError`  
 Ein Zeiger auf eine vorhandene Datei-Exception-Objekt, das den Status eines fehlgeschlagenen Vorgangs erhalten.  
  
 `pTM`  
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="readstring"></a>CStdioFile::ReadString  
 Liest Textdaten in einen Puffer, bis zu einem Höchstwert von `nMax`-1-Zeichen aus der Datei zugeordneten der `CStdioFile` Objekt.  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Gibt einen Zeiger auf einen Benutzer bereitgestellte Puffer, der eine Null-terminierte Zeichenfolge erhalten.  
  
 `nMax`  
 Gibt die maximale Anzahl von Zeichen zu lesen, das abschließende Null-Zeichen wird dabei nicht mitgezählt.  
  
 `rString`  
 Ein Verweis auf ein `CString` -Objekt, das die Zeichenfolge enthält bei Rückgabe der Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Puffer mit Daten aus der Textdatei. **NULL** Wenn Ende der Datei erreicht wurde, ohne alle Daten lesen oder Boolesch, **FALSE** Wenn das Ende der Datei erreicht wurde, ohne alle Daten zu lesen.  
  
### <a name="remarks"></a>Hinweise  
 Lesen wird nach dem ersten neue Zeilenumbruchzeichen beendet. Wenn in diesem Fall, weniger als `nMax`–&1; Zeichen gelesen wurden, ein neue Zeilenumbruchzeichen im Puffer gespeichert wird. In beiden Fällen wird ein Null-Zeichen ('\0') angefügt.  
  
 [CFile:: Read](../../mfc/reference/cfile-class.md#read) steht auch für die Eingabe von Text-Modus, aber es wird nicht für eine Kombination aus Wagenrücklauf und Zeilenvorschub beendet.  
  
> [!NOTE]
>  Die `CString` Version dieser Funktion entfernt die `'\n'` falls vorhanden; die `LPTSTR` Version nicht der Fall.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#38;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="seek"></a>CStdioFile::Seek  
 Verschiebt den Zeiger in einer bereits geöffneten Datei.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Parameter  
 `lOff`  
 Anzahl der Bytes, die mit der Maus.  
  
 `nFrom`  
 Zeiger verschieben-Modus. Dabei muss es sich um einen der folgenden Werte sein:  
  
- `CFile::begin`: Den Dateizeiger verschoben `lOff` Bytes vom Anfang der Datei weitergeleitet.  
  
- `CFile::current`: Den Dateizeiger verschoben `lOff` Bytes aus der aktuellen Position in der Datei.  
  
- `CFile::end`: Den Dateizeiger verschoben `lOff` Bytes vom Ende der Datei. Beachten Sie, dass `lOff` muss werden Negative, Suchen in der vorhandenen Datei; positive Werte nach dem Ende der Datei gesucht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die angeforderte Position rechtliche `Seek` gibt das neuen Byte-Offset vom Anfang der Datei. Andernfalls ist der Rückgabewert nicht definiert und ein `CFileException` Objekt ausgelöst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die `Seek` Funktion ermöglicht den wahlfreien Zugriff auf den Inhalt einer Datei durch Bewegen des Mauszeigers einen angegebenen Betrag, absolut oder relativ. Während der Suche ist keine Daten gelesen. Ist die angeforderte Position größer als die Größe der Datei, die Dateilänge an diese Position erweitert werden, und es wird keine Ausnahme ausgelöst.  
  
 Wenn eine Datei geöffnet wird, wird der Dateizeiger am Offset 0 ist, am Anfang der Datei positioniert.  
  
 Diese Implementierung der `Seek` basiert auf der Run-Time Library (CRT)-Funktion `fseek`. Es gibt mehrere Einschränkungen für die Verwendung des `Seek` Datenströme, die im Textmodus geöffnet wurden. Weitere Informationen finden Sie unter [fseek-und _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie `Seek` zum Verschieben des Cursors 1000 Bytes vom Anfang der `cfile` Datei. Beachten Sie, dass `Seek` Daten werden nicht gelesen werden, damit Sie später aufrufen müssen [CStdioFile::ReadString](#readstring) zum Lesen von Daten.  
  
 [!code-cpp[NVC_MFCFiles Nr.&39;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="writestring"></a>CStdioFile::WriteString  
 Schreibt Daten aus einem Puffer auf die Datei mit den `CStdioFile` Objekt.  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Gibt einen Zeiger auf einen Puffer, der eine Null-terminierte Zeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das abschließende Nullzeichen ( `\0`) nicht in die Datei geschrieben. Diese Methode schreibt Zeilenumbruchzeichen `lpsz` in die Datei als Wagenrücklauf/Zeilenvorschub-Paar.  
  
 Zum Schreiben von Daten, die nicht in eine Datei, die mit Null-terminiert ist ggf. `CStdioFile::Write` oder [CFile::Write](../../mfc/reference/cfile-class.md#write).  
  
 Diese Methode löst eine `CInvalidArgException*` bei Angabe `NULL` für die `lpsz` Parameter.  
  
 Diese Methode löst eine `CFileException*` Reaktion auf Fehler im Dateisystem.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#40;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)

