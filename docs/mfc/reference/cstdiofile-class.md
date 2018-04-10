---
title: CStdioFile Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 868442a2936781ed24588f47dcb591cadcc48f0d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="cstdiofile-class"></a>CStdioFile-Klasse
Eine C-Laufzeit-streamdatei dar, der von der Funktion zur Laufzeit geöffnet [Fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
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
|[CStdioFile::Open](#open)|Überladen. Open dient zur Verwendung mit der standardmäßigen `CStdioFile` Konstruktor (Außerkraftsetzungen [CFile::Open](../../mfc/reference/cfile-class.md#open)).|  
|[CStdioFile::ReadString](#readstring)|Liest eine einzelne Textzeile.|  
|[CStdioFile::Seek](#seek)|Positioniert den Zeiger auf den aktuellen Datei an.|  
|[CStdioFile::WriteString](#writestring)|Schreibt eine einzelne Textzeile.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|Enthält einen Zeiger auf eine geöffnete Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Stream-Dateien werden gepuffert und können im Textmodus (Standard) oder Binärmodus geöffnet werden.  
  
 SMS-Modus bietet spezielle Verarbeitung für Wagenrücklauf-Return-Zeilenvorschub-Paare. Beim Schreiben eines Zeilenvorschubs Zeichen (0x0A) in einen Text-Modus `CStdioFile` -Objekt, das Paar Byte (0x0D, 0x0A) wird in der Datei gesendet. Wenn Sie diese gelesen und das Paar Byte (0x0D, 0x0A) wird in ein einzelnes Byte an 0x0A übersetzt.  
  
 Die [CFile](../../mfc/reference/cfile-class.md) Funktionen [doppelte](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), und [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) können nicht für `CStdioFile`.  
  
 Wenn Sie für diese Funktionen aufrufen einer `CStdioFile`, erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Weitere Informationen zur Verwendung von `CStdioFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
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
 `pOpenStream`  
 Gibt an, den Dateizeiger zurückgegeben, die durch einen Aufruf der C-Laufzeitbibliotheksfunktion [Fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 `lpszFileName`  
 Gibt eine Zeichenfolge, die den Pfad zu der gewünschten Datei ist. Der Pfad kann relativ oder absolut sein.  
  
 `nOpenFlags`  
 Gibt Optionen für die Erstellung, Freigabe von Dateien und Zugriffsmodi für die Datei. Sie können mehrere Optionen angeben, mit den bitweisen OR-Operator ( `|`) Operator.  
  
 Eine Datei im Modus Zugriffsoption ist erforderlich; andere Modi sind optional. Finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) eine Liste der Optionen und andere Flags. In MFC, Version 3.0 und höher sind Freigabe Flags zulässig.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor wird nicht zu eine Datei angefügt der `CStdioFile` Objekt. Wenn Sie diesen Konstruktor verwenden, müssen Sie verwenden die `CStdioFile::Open` Methode, um eine Datei öffnen, und fügen Sie es auf die `CStdioFile` Objekt.  
  
 Der Konstruktor für die einzelnen Parameter fügt zu einen Datei öffnen-Stream der `CStdioFile` Objekt. Zulässige Zeigerwerte enthalten, die Dateizeiger für das vordefinierte e/a- `stdin`, `stdout`, oder `stderr`.  
  
 Die beiden Parameter-Konstruktor erstellt ein `CStdioFile` Objekt, und die entsprechende Datei geöffnet, mit dem angegebenen Pfad.  
  
 Wenn Sie übergeben `NULL` entweder `pOpenStream` oder `lpszFileName`, löst der Konstruktor eine `CInvalidArgException*`.  
  
 Wenn die Datei geöffnet oder erstellt werden kann nicht, löst der Konstruktor eine `CFileException*`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="m_pstream"></a>  CStdioFile::m_pStream  
 Die `m_pStream` Datenelement ist der Zeiger auf eine geöffnete Datei an, wie die C-Laufzeit-Funktion zurückgegeben `fopen`.  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist **NULL** Wenn die Datei nicht geöffnet wurde oder geschlossen wurde.  
  
##  <a name="open"></a>  CStdioFile::Open  
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
 Eine Zeichenfolge, die den Pfad zu der gewünschten Datei ist. Der Pfad kann relativ oder absolut sein.  
  
 `nOpenFlags`  
 Freigabe und Zugriffsmodus. Gibt die zu ergreifende Maßnahme beim Öffnen der Datei an. Sie können Optionen kombinieren, mit dem bitweisen OR-(&#124;) Operator. Eine Access-Berechtigung und eine Freigabe Option sind erforderlich. die Modi ModeCreate und ModeNoInherit sind optional.  
  
 `pError`  
 Ein Zeiger auf ein vorhandenes Datei-Ausnahme-Objekt, das den Status eines fehlgeschlagenen Vorgangs erhält.  
  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="readstring"></a>  CStdioFile::ReadString  
 Liest Textdaten in einen Puffer, bis zu einem Höchstwert von `nMax`-1 Zeichen aus der Datei zugeordneten der `CStdioFile` Objekt.  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Gibt einen Zeiger auf einen Benutzer bereitgestellte Puffer, der eine Null-terminierte Zeichenfolge empfangen.  
  
 `nMax`  
 Gibt an, dass die maximale Anzahl von Zeichen zu lesen, das abschließende Null-Zeichen wird dabei nicht mitgezählt.  
  
 `rString`  
 Ein Verweis auf eine `CString` -Objekt, das die Zeichenfolge enthalten soll, wenn die Funktion zurückgibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Puffer, der Textdaten enthält. **NULL** Wenn Ende der Datei erreicht wurde, ohne Lesen von Daten; oder wenn boolean **"false"** Wenn Ende der Datei erreicht wurde, ohne alle Daten zu lesen.  
  
### <a name="remarks"></a>Hinweise  
 Lesen wird durch die erste neue Zeilenumbruchzeichen beendet. Wenn in diesem Fall, weniger als `nMax`-1 Zeichen gelesen wurden, ein neue Zeilenumbruchzeichen im Puffer gespeichert ist. In beiden Fällen wird ein Null-Zeichen ('\0') angefügt.  
  
 [CFile:: Read](../../mfc/reference/cfile-class.md#read) ist auch verfügbar, für die Textmodus Eingabe, sondern es wird nicht auf eine Carriage Return-Zeilenvorschub beendet.  
  
> [!NOTE]
>  Die `CString` Version dieser Funktion entfernt die `'\n'` angefordertes; die `LPTSTR` Version nicht unterstützt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="seek"></a>  CStdioFile::Seek  
 Verschiebt den Zeiger in einer zuvor geöffneten Datei.  
  
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
  
- `CFile::begin`: Verschieben den Dateizeiger `lOff` Bytes vom Anfang der Datei weiterleiten.  
  
- `CFile::current`: Verschieben den Dateizeiger `lOff` Bytes aus der aktuellen Position in der Datei.  
  
- `CFile::end`: Verschieben den Dateizeiger `lOff` Bytes aus dem Ende der Datei. Beachten Sie, dass `lOff` müssen werden Negative zu suchende in die vorhandene Datei; positive Werte nach dem Ende der Datei gesucht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die angeforderte Position rechtliche ist `Seek` das neuen Byte-Offset vom Anfang der Datei zurückgegeben. Andernfalls ist der Rückgabewert nicht definiert und eine `CFileException` Objekt ausgelöst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die `Seek` -Funktion ermöglicht wahlfreien Zugriff auf den Inhalt einer Datei durch den Mauszeiger über einen bestimmten Zeitraum, absolut oder relativ. Keine Daten werden tatsächlich während der Seek gelesen. Wenn die angeforderte Position größer als die Größe der Datei ist, wird die Dateilänge dieser Position erweitert werden und wird keine Ausnahme ausgelöst werden.  
  
 Wenn eine Datei geöffnet wird, wird der Dateizeiger am Offset 0 (null) den Anfang der Datei positioniert.  
  
 Diese Implementierung der `Seek` basiert auf der Run-Time Library (CRT)-Funktion `fseek`. Es gibt mehrere Einschränkungen auf der Nutzung von `Seek` Datenstreams im Textmodus geöffnet. Weitere Informationen finden Sie unter [fseek-und _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie `Seek` zum Verschieben des Cursors 1000 Bytes vom Anfang der `cfile` Datei. Beachten Sie, dass `Seek` Daten werden nicht gelesen werden, damit Sie später aufrufen müssen [CStdioFile::ReadString](#readstring) zum Lesen von Daten.  
  
 [!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="writestring"></a>  CStdioFile::WriteString  
 Schreibt Daten aus einem Puffer, an die zugeordnete Datei die `CStdioFile` Objekt.  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Gibt einen Zeiger auf einen Puffer, der eine Null-terminierte Zeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das abschließende Nullzeichen ( `\0`) ist nicht in die Datei geschrieben. Diese Methode schreibt Zeilenumbruchzeichen `lpsz` in die Datei als Wagenrücklauf/Zeilenvorschub-Paar.  
  
 Wenn Sie Daten zu schreiben, die nicht in eine Datei, die mit Null-terminierte möchten `CStdioFile::Write` oder [CFile::Write](../../mfc/reference/cfile-class.md#write).  
  
 Diese Methode löst eine `CInvalidArgException*` bei Angabe von `NULL` für die `lpsz` Parameter.  
  
 Diese Methode löst eine `CFileException*` als Antwort auf Fehler im Dateisystem.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)
