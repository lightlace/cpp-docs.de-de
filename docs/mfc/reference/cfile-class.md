---
title: CFile-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CFile class
- CArchive class, using with CFile
- files [C++], classes for
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
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
ms.openlocfilehash: bc6edf87e5653a6aa8c749a4574c5b50fdae75a0
ms.lasthandoff: 02/24/2017

---
# <a name="cfile-class"></a>CFile-Klasse
Die Basisklasse für Microsoft Foundation Class-Dateiklassen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFile : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFile::CFile](#cfile)|Erstellt ein `CFile` Objekt aus einem Pfad oder Datei-Handle.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFile::Abort](#abort)|Schließt eine Datei, die alle Warnungen und Fehler werden ignoriert.|  
|[CFile::Close](#close)|Schließt eine Datei und löscht das Objekt.|  
|[CFile::Duplicate](#duplicate)|Erstellt ein doppeltes Objekt, das auf der Grundlage dieser Datei.|  
|[CFile::Flush](#flush)|Löscht alle Daten, die noch zu.|  
|[CFile::GetFileName](#getfilename)|Ruft den Dateinamen der ausgewählten Datei.|  
|[CFile::GetFilePath](#getfilepath)|Ruft den vollständigen Dateipfad der ausgewählten Datei.|  
|[CFile::GetFileTitle](#getfiletitle)|Ruft den Titel der ausgewählten Datei.|  
|[CFile::GetLength](#getlength)|Ruft die Länge der Datei ab.|  
|[CFile::GetPosition](#getposition)|Ruft die aktuelle Dateizeiger ab.|  
|[CFile:: GetStatus](#getstatus)|Ruft den Status der geöffneten Datei oder in die statische Version ab, wird der Status der angegebenen Datei (statische, virtuelle Funktion).|  
|[CFile::LockRange](#lockrange)|Sperren ein Bereichs von Bytes in einer Datei.|  
|[CFile::Open](#open)|Sicher öffnet eine Datei mit der Option Fehler testen.|  
|[CFile:: Read](#read)|Lesevorgänge (ungepufferte) Daten aus einer Datei an der aktuellen Dateiposition.|  
|[CFile::Remove](#remove)|Löscht die angegebene Datei (statische Funktion).|  
|[CFile::Rename](#rename)|Benennt die angegebene Datei (statische Funktion).|  
|[CFile::Seek](#seek)|Positioniert den Zeiger auf den aktuellen Datei.|  
|[CFile::SeekToBegin](#seektobegin)|Positioniert den Zeiger auf den aktuellen Datei am Anfang der Datei.|  
|[CFile::SeekToEnd](#seektoend)|Positioniert den aktuellen Dateizeiger am Ende der Datei.|  
|[CFile::SetFilePath](#setfilepath)|Legt den vollständigen Pfad der ausgewählten Datei.|  
|[CFile::SetLength](#setlength)|Ändert die Länge der Datei.|  
|[CFile::SetStatus](#setstatus)|Setzt den Status der angegebenen Datei (statische, virtuelle Funktion).|  
|[CFile::UnlockRange](#unlockrange)|Hebt die Sperre eines Bereichs von Bytes in einer Datei.|  
|[CFile::Write](#write)|(Ungepufferte) Schreiben von Daten in einer Datei, die aktuelle Dateiposition.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFile::operator HANDLE](#operator_handle)|Ein Handle für ein `CFile` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFile::hFileNull](#hfilenull)|Bestimmt, ob die `CFile` -Objekt verfügt über ein gültiges Handle.|  
|[CFile::m_hFile](#m_hfile)|In der Regel enthält das Dateihandle des Betriebssystems.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Es bietet direkt nicht zwischengespeicherten, binäre Datenträger Eingabe/Ausgabe-Dienste und indirekt Textdateien und Speicher über die abgeleiteten Klassen unterstützt. `CFile`funktioniert in Verbindung mit der `CArchive` Klasse zur Unterstützung der Serialisierung der Microsoft Foundation Class-Objekte.  
  
 Die hierarchische Beziehung zwischen dieser Klasse und ihrer abgeleiteten Klassen kann Ihr Programm funktioniert für alle Dateiobjekte über die polymorphe `CFile` Schnittstelle. Eine Arbeitsspeicherdatei verhält sich z. B. wie eine Datenträgerdatei.  
  
 Verwendung `CFile` und abgeleitete Klassen für allgemeine Datenträger-e/a. Verwendung `ofstream` oder andere Microsoft-Iostream-Klassen für formatierten Text in eine Datei gesendet.  
  
 Eine Datei wird in der Regel automatisch geöffnet `CFile` Konstruktion und Zerstörung geschlossen. Statische Member-Funktionen können Sie Status einer Datei abzufragen, ohne die Datei zu öffnen.  
  
 Weitere Informationen zur Verwendung von `CFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="abort"></a>CFile::Abort  
 Schließt die Datei, die diesem Objekt zugeordnet und wird die Datei zum Lesen oder Schreiben nicht verfügbar.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Datei nicht vor dem Löschen des Objekts geschlossen haben, wird es von der Destruktor geschlossen.  
  
 Beim Verarbeiten von Ausnahmen, `CFile::Abort` unterscheidet sich von `CFile::Close` in zwei wichtigen Aspekten. Zuerst die **Abort** Funktion nicht löst eine Ausnahme bei Fehlern da Fehler, indem ignoriert werden **Abort**. Zweitens **Abort** nicht **ASSERT** Datei wurde nicht geöffnet oder wurde bereits geschlossen.  
  
 Wenn Sie verwendet **neue** Zuweisen der `CFile` -Objekt im Heap, Sie nach dem Schließen der Datei gelöscht werden müssen. **Abort** sets `m_hFile` to `CFile::hFileNull`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&5;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]  
  
##  <a name="cfile"></a>CFile::CFile  
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
 `hFile`  
 Handle einer Datei zum Anhängen an das `CFile`-Objekt.  
  
 `lpszFileName`  
 Relativer oder vollständiger Pfad einer Datei zum Anhängen an das `CFile`-Objekt.  
  
 `nOpenFlags`  
 Bitweise Kombination (OR) der Dateizugriffsoptionen für die angegebene Datei. Mögliche Optionen finden Sie im Abschnitt "Hinweise".  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Die folgenden fünf Tabellen enthalten die möglichen Optionen für die `nOpenFlags`-Parameter.  
  
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
|`CFile::typeText`|Legt den Textmodus mit spezieller Verarbeitung für Wagenrücklauf-Zeilenvorschub-Paare fest (nur in abgeleiteten Klassen verwendet).|  
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
|`CFile::modeCreate`|Erstellt eine neue Datei, wenn keine Datei vorhanden ist.; Wenn die Datei bereits vorhanden ist, [CFileException](../../mfc/reference/cfileexception-class.md) ausgelöst wird.|  
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
  
 Der Standardkonstruktor initialisiert Member, hängt jedoch keine Datei an das `CFile`-Objekt an. Verwenden Sie nach der Verwendung des Konstruktors der [CFile::Open](#open) Methode, um eine Datei öffnen, und fügen Sie es auf die `CFile` Objekt.  
  
 Der Konstruktor mit einem Parameter initialisiert Member und hängt eine vorhandene Datei an das `CFile`-Objekt an.  
  
 Der Konstruktor mit zwei Parametern initialisiert Member und versucht, die angegebene Datei zu öffnen. Wenn der Konstruktor die angegebene Datei erfolgreich öffnet, wird die Datei an das `CFile`-Objekt angehängt; anderenfalls löst der Konstruktor einen Zeiger auf ein `CInvalidArgException`-Objekt aus. Weitere Informationen zum Behandeln von Ausnahmen finden Sie unter [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
 Wenn ein `CFile`-Objekt eine angegebene Datei erfolgreich öffnet, wird diese Datei automatisch geschlossen, wenn das `CFile`-Objekt zerstört wird; anderenfalls müssen Sie die Datei explizit schließen, wenn sie nicht mehr an das `CFile`-Objekt angehängt ist.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht die Verwendung einer `CFile`.  
  
 [!code-cpp[NVC_MFCFiles&4;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]  
  
##  <a name="close"></a>CFile::Close  
 Schließt die Datei, die diesem Objekt zugeordnet und wird die Datei zum Lesen oder Schreiben nicht verfügbar.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Datei nicht vor dem Löschen des Objekts geschlossen haben, wird es von der Destruktor geschlossen.  
  
 Wenn Sie verwendet **neue** Zuweisen der `CFile` -Objekt im Heap, Sie nach dem Schließen der Datei gelöscht werden müssen. **Close** sets `m_hFile` to `CFile::hFileNull`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::CFile](#cfile).  
  
##  <a name="duplicate"></a>CFile::Duplicate  
 Erstellt ein Duplikat `CFile` Objekt für eine bestimmte Datei.  
  
```  
virtual CFile* Duplicate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Duplikat `CFile` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist gleichbedeutend mit der C-Laufzeitfunktion `_dup`.  
  
##  <a name="flush"></a>CFile::Flush  
 Erzwingt, dass alle Daten in der Dateipuffer in die Datei geschrieben werden.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Verwendung von `Flush` garantiert keine leeren des `CArchive` Puffer. Wenn Sie ein Archiv verwenden, rufen Sie [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) ersten.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::SetFilePath](#setfilepath).  
  
##  <a name="getfilename"></a>CFile::GetFileName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens einer angegebenen Datei.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. beim Aufruf `GetFileName` zum Generieren einer Nachricht an den Benutzer über die Datei `c:\windows\write\myfile.wri`, den Dateinamen `myfile.wri`, zurückgegeben.  
  
 Rufen Sie den vollständigen Pfad der Datei, einschließlich des Namens zurückgeben [GetFilePath](#getfilepath). Den Titel der Datei zurückgegeben ( `myfile`), rufen Sie [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment wird vom SYSTEM geöffnet. INI-Datei im WINDOWS-Verzeichnis. Wenn gefunden, im Beispiel wird der Name und der Pfad und der Titel Drucken wird wie unter Ausgabe angezeigt:  
  
 [!code-cpp[NVC_MFCFiles&6;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]  
  
##  <a name="getfilepath"></a>CFile::GetFilePath  
 Rufen Sie diese Memberfunktion rufen Sie den vollständigen Pfad einer angegebenen Datei.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vollständige Pfad der angegebenen Datei.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. beim Aufruf `GetFilePath` zum Generieren einer Nachricht an den Benutzer über die Datei `c:\windows\write\myfile.wri`, den Dateipfad `c:\windows\write\myfile.wri`, zurückgegeben.  
  
 Nur der Name der Datei zurückgegeben ( `myfile.wri`), rufen Sie [GetFileName](#getfilename). Den Titel der Datei zurückgegeben ( `myfile`), rufen Sie [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>CFile::GetFileTitle  
 Rufen Sie diese Memberfunktion zum Abrufen des Titels (Anzeigename) für die Datei.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel des zugrunde liegenden Datei.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) um den Titel der Datei abzurufen. Bei erfolgreicher Ausführung gibt die Methode die Zeichenfolge, die das System verwendet den Dateinamen für den Benutzer anzuzeigen. Andernfalls, ruft die Methode [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) zum Abrufen des Dateinamens (einschließlich Erweiterung) der zugrunde liegenden Datei. Daher wird die Erweiterung nicht immer in der zurückgegebenen Titelzeichenfolge enthalten sein. Weitere Informationen finden Sie unter [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) und [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Rufen Sie den vollständigen Pfad der Datei, einschließlich des Namens zurückgeben [GetFilePath](#getfilepath). Rufen Sie zum Zurückgeben der nur der Name der Datei [GetFileName](#getfilename).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetFileName](#getfilename).  
  
##  <a name="getlength"></a>CFile::GetLength  
 Ruft die aktuelle logische Länge der Datei in Bytes ab.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Datei.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#7;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]  
  
##  <a name="getposition"></a>CFile::GetPosition  
 Ruft den aktuellen Wert des Dateizeigers, die bei nachfolgenden Aufrufen von verwendet werden können `Seek`.  
  
```  
virtual ULONGLONG GetPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Dateizeiger.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#8;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]  
  
##  <a name="getstatus"></a>CFile:: GetStatus  
 Diese Methode ruft Statusinformationen, die im Zusammenhang mit einer bestimmten `CFile` Objektinstanz oder der Pfad zu einer bestimmten Datei.  
  
```  
BOOL GetStatus(CFileStatus& rStatus) const;  
  
static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,  
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rStatus`  
 Ein Verweis auf eine vom Benutzer bereitgestellte **CFileStatus** -Struktur, die die Statusinformationen zu erhalten. Die **CFileStatus** Struktur enthält die folgenden Felder:  
  
- **CTime M_ctime** Datum und Uhrzeit die Datei erstellt wurde.  
  
- **CTime M_mtime** Datum und Uhrzeit der letzten der Datei Änderung.  
  
- **CTime M_atime** Datum und Uhrzeit der letzten Zugriff auf die Datei zum Lesen.  
  
- **ULONGLONG M_size** die logische Größe der Datei in Bytes, der von der Befehl DIR gemeldet.  
  
- **BYTE-M_attribute** das Attribut Byte der Datei.  
  
- **M_szFullName [_MAX_PATH] char** den absoluten Dateinamen in der Windows-Zeichensatz.  
  
 `lpszFileName`  
 Eine Zeichenfolge in das Windows-Zeichen legen Sie den Pfad, um die gewünschte Datei. Der Pfad kann relativ oder absolut sein, oder ein Netzwerkpfad enthalten.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist die Statusinformationen für die angegebene Datei erfolgreich abgerufen wurde; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die nicht statische Version der **GetStatus** ruft Statusinformationen der geöffneten Datei zugeordnet der angegebenen `CFile` Objekt.  Die statische Version **GetStatus** erhält den Status der Datei aus einem angegebenen Pfad ohne die Datei öffnen. Dies ist nützlich für das Vorhandensein und die Zugriffsrechte einer Datei zu testen.  
  
 Die **M_attribute** Mitglied der **CFileStatus** Struktur bezieht sich auf die Datei-Attribut. Die `CFile` -Klasse stellt die **Attribut** Enumerationstyp also Dateiattribute symbolisch angegeben werden können:  
  
 `enum Attribute {`  
  
 `normal =    0x00,`  
  
 `readOnly =  0x01,`  
  
 `hidden =    0x02,`  
  
 `system =    0x04,`  
  
 `volume =    0x08,`  
  
 `directory = 0x10,`  
  
 `archive =   0x20`  
  
 `};`  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#10;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]  
  
##  <a name="hfilenull"></a>CFile::hFileNull  
 Bestimmt das Vorhandensein eines gültigen Dateihandles für die `CFile` Objekt.  
  
```  
static AFX_DATA const HANDLE hFileNull;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Konstante wird verwendet, um festzustellen, ob die `CFile` -Objekt verfügt über einen gültigen Dateihandles.  
  
 Das folgende Beispiel veranschaulicht diesen Vorgang:  
  
 [!code-cpp[NVC_MFCFiles&#22;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]  
  
##  <a name="lockrange"></a>CFile::LockRange  
 Sperren ein Bereichs von Bytes in eine Datei öffnen, die eine Ausnahme auszulösen, wenn die Datei bereits gesperrt ist.  
  
```  
virtual void LockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Parameter  
 `dwPos`  
 Der Offset in Bytes vom Anfang des zu sperrenden Bytebereichs.  
  
 `dwCount`  
 Die Anzahl der Bytes in der zu sperrenden Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehrere Bereiche einer Datei sperren, jedoch keine überlappenden Bereiche sind zulässig.  
  
 Wenn Sie die Region entsperren, mithilfe der `UnlockRange` -Memberfunktion der Bytebereich muss genau in der Region, die zuvor gesperrt war entsprechen. Die `LockRange` Funktion nicht benachbarte Bereiche zusammen, wenn zwei gesperrte Bereiche nebeneinander angeordnet sind, müssen Sie jeden Bereich einzeln freigeben.  
  
> [!NOTE]
>  Diese Funktion ist nicht verfügbar für die `CMemFile`-Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#12;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="m_hfile"></a>CFile::m_hFile  
 Enthält den Betriebssystem Dateihandle für eine geöffnete Datei.  
  
```  
HANDLE m_hFile;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_hFile`ist eine öffentliche Variable des Typs **UINT**. Es enthält `CFile::hFileNull` (eine leere Datei Betriebssystem-System-unabhängigen Indicator) Wenn das Handle nicht zugewiesen wurde.  
  
 Verwenden von `m_hFile` wird nicht empfohlen, da die abgeleitete Klasse Bedeutung für das Element abhängig. `m_hFile`erfolgt einen öffentlichen Member der Einfachheit halber bei der Unterstützung von nicht polymorphen der Klasse verwenden.  
  
##  <a name="m_ptm"></a>CFile::m_pTM  
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="open"></a>CFile::Open  
 Überladen. **Öffnen Sie** dient zur Verwendung mit der standardmäßigen `CFile` Konstruktor.  
  
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
 Eine Zeichenfolge, die den Pfad zur gewünschten Datei. Der Pfad kann es sich um Relative, Absolute oder einen Netzwerknamen (UNC) sein.  
  
 `nOpenFlags`  
 Ein **UINT** , definiert die Datei freigeben und Zugriffsmodus. Es gibt die Aktion an, der beim Öffnen der Datei. Sie können Optionen kombinieren, indem Sie mit dem bitweisen OR ( **|** ) Operator. Eine Access-Berechtigung und eine Freigabe-Option ist erforderlich. die **ModeCreate** und **ModeNoInherit** Modi sind optional. Finden Sie unter der [CFile](#cfile) Konstruktor für eine Liste der Optionen für den Modus.  
  
 `pError`  
 Ein Zeiger auf eine vorhandene Datei-Exception-Objekt, das den Status eines fehlgeschlagenen Vorgangs erhalten.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Öffnungsvorgang erfolgreich war; andernfalls 0. Die `pError` Parameter ist nur sinnvoll, wenn 0 zurückgegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Die beiden Funktionen bilden eine "sichere" Methode zum Öffnen einer Datei, in denen eine normale, erwartete Bedingung ist.  
  
 Während der `CFile` Konstruktors löst eine Ausnahme in einen Fehlerzustand **öffnen** zurück **FALSE** Fehlerzustände. **Öffnen Sie** können weiterhin Initialisieren einer [CFileException](../../mfc/reference/cfileexception-class.md) Objekt, um den Fehler jedoch zu beschreiben. Wenn Sie angeben der `pError` -Parameter, oder übergeben **NULL** für `pError`, **öffnen** zurück **FALSE** und löst eine `CFileException`. Wenn Sie einen Zeiger auf ein vorhandenes übergeben `CFileException`, und **öffnen** einen Fehler erkennt, die Funktion füllt es mit Informationen, die den Fehler beschreibt. Weder Case wird **öffnen** löst eine Ausnahme aus.  
  
 Die folgende Tabelle beschreibt die möglichen Ergebnisse **öffnen**.  
  
|`pError`|Fehler:|Rückgabewert|CFileException Inhalt|  
|--------------|------------------------|------------------|----------------------------|  
|**NULL**|Nein|**"TRUE"**|nicht verfügbar|  
|Zeiger auf`CFileException`|Nein|**"TRUE"**|unverändert|  
|**NULL**|Ja|**FALSE**|nicht verfügbar|  
|Zeiger auf`CFileException`|Ja|**FALSE**|Initialisiert, um Fehler zu beschreiben|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#13;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCFiles&14;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]  
  
##  <a name="operator_handle"></a>CFile::operator HANDLE  
 Verwenden Sie diesen Operator übergeben Sie ein Handle für ein `CFile` object Funktionen wie z. B. [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) und [GetFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724320) , die erwarten, dass ein `HANDLE`.  
  
```  
operator HANDLE() const;  
```  
  
##  <a name="read"></a>CFile:: Read  
 Liest Daten in einen Puffer aus der Datei zugeordneten der `CFile` Objekt.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Zeiger auf den Benutzer bereitgestellte Puffer, der die Daten empfängt, die aus der Datei gelesen werden.  
  
 `nCount`  
 Die maximale Anzahl von Bytes aus der Datei gelesen werden. Für Dateien, Textmodus Wagenrücklauf-Zeilenvorschub-Paare als einzelne Zeichen gezählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in den Puffer übertrageben Bytes. Beachten Sie, dass für alle `CFile` Klassen, ist der Rückgabewert möglicherweise kleiner als `nCount` , wenn das Ende der Datei erreicht wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#15;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CFile::Open](#open).  
  
##  <a name="remove"></a>CFile::Remove  
 Diese statischen Funktion löscht die durch den Pfad angegebene Datei.  
  
```  
static void PASCAL Remove(
    LPCTSTR lpszFileName, 
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zur gewünschten Datei. Der Pfad kann relativ oder absolut sein und kann einen Netzwerknamen enthalten.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Es wird ein Verzeichnis nicht entfernt.  
  
 Die **entfernen** Memberfunktion löst eine Ausnahme aus, wenn die verbundene Datei geöffnet ist oder die Datei kann nicht entfernt werden. Dies entspricht dem Befehl DEL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&17;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]  
  
##  <a name="rename"></a>CFile::Rename  
 Die statische Funktion benennt die angegebene Datei.  
  
```  
static void PASCAL Rename(
    LPCTSTR lpszOldName,  
    LPCTSTR lpszNewName,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszOldName`  
 Der alte Pfad.  
  
 `lpszNewName`  
 Der neue Pfad.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Verzeichnisse können nicht umbenannt werden. Dies ist äquivalent zum Befehl REN.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&18;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]  
  
##  <a name="seek"></a>CFile::Seek  
 Positioniert die Datei in eine geöffnete Datei.  
  
```  
virtual ULONGLONG Seek(
LONGLONG lOff,  
UINT nFrom);
```  
  
### <a name="parameters"></a>Parameter  
 `lOff`  
 Anzahl der Bytes den Dateizeiger verschoben. Positive Werte verschieben den Dateizeiger am Ende der Datei; negative Werte verschieben den Dateizeiger an den Anfang der Datei.  
  
 `nFrom`  
 Die Position von gesucht. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des Dateizeigers, wenn die Methode erfolgreich war; Andernfalls ist der Rückgabewert nicht definiert und einen Zeiger auf eine `CFileException` Ausnahme ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nFrom` Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CFile::begin`|Suchen Sie am Anfang der Datei.|  
|`CFile::current`|Suchen Sie von der aktuellen Position des Dateizeigers.|  
|`CFile::end`|Suchen Sie am Ende der Datei.|  
  
 Wenn eine Datei geöffnet wird, wird der Dateizeiger bei 0 und den Anfang der Datei positioniert.  
  
 Sie können den Dateizeiger an eine Stelle hinter dem Ende der Datei festlegen. Wenn Sie dies tun, wird die Größe der Datei nicht erhöhen, bis in die Datei geschrieben werden.  
  
 Der Ausnahmehandler für diese Methode muss das Ausnahmeobjekt löschen, nachdem die Ausnahme verarbeitet wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#9;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]  
  
##  <a name="seektobegin"></a>CFile::SeekToBegin  
 Legt den Wert der Dateizeiger am Anfang der das fest.  
  
```  
void SeekToBegin();
```  
  
### <a name="remarks"></a>Hinweise  
 `SeekToBegin()` entspricht `Seek( 0L, CFile::begin )`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles Nr.&19;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="seektoend"></a>CFile::SeekToEnd  
 Legt den Wert des Dateizeigers auf das logische Ende der Datei fest.  
  
```  
ULONGLONG SeekToEnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Datei in Byte.  
  
### <a name="remarks"></a>Hinweise  
 `SeekToEnd()` entspricht `CFile::Seek( 0L, CFile::end )`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles Nr.&19;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="setfilepath"></a>CFile::SetFilePath  
 Rufen Sie diese Funktion, um den Pfad der Datei angeben. beispielsweise, wenn der Pfad einer Datei nicht verfügbar bei einer [CFile](../../mfc/reference/cfile-class.md) Objekt erstellt wurde, rufen Sie `SetFilePath` zur Verfügung stellt.  
  
```  
virtual void SetFilePath(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewName`  
 Zeiger auf eine Zeichenfolge, die den neuen Pfad angeben.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> `SetFilePath`nicht öffnen Sie die Datei oder erstellen Sie die Datei; es einfach ordnet die `CFile` Objekt mit einem Pfadnamen, die dann verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&20;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]  
  
##  <a name="setlength"></a>CFile::SetLength  
 Rufen Sie diese Funktion, um die Länge der Datei zu ändern.  
  
```  
virtual void SetLength(ULONGLONG dwNewLen);
```  
  
### <a name="parameters"></a>Parameter  
 `dwNewLen`  
 Die gewünschte Länge der Datei in Byte. Dieser Wert kann größer oder kleiner als die aktuelle Länge der Datei sein. Die Datei werden erweitert oder nach Bedarf abgeschnitten.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Mit `CMemFile`, kann diese Funktion Auslösen einer `CMemoryException` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#11;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]  
  
##  <a name="setstatus"></a>CFile::SetStatus  
 Setzt den Status der Datei zugeordneten Speicherort dieser Datei.  
  
```  
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,  
    const CFileStatus& status,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zur gewünschten Datei. Der Pfad kann relativ oder absolut sein und kann einen Netzwerknamen enthalten.  
  
 *status*  
 Der Puffer mit den neuen Informationen. Rufen Sie die **GetStatus** Memberfunktion prefill der **CFileStatus** Struktur mit aktuellen Werten, und ändern Sie dann nach Bedarf. Wenn der Wert 0 ist, wird das entsprechende Element der Status nicht aktualisiert. Finden Sie unter der [GetStatus](#getstatus) Member-Funktion eine Beschreibung der **CFileStatus** Struktur.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie zum Festlegen der Uhrzeit der **M_mtime** Feld *Status*.  
  
 Beachten Sie, dass wenn Sie einen Aufruf `SetStatus` versuchen, nur die Attribute der Datei ändern und die **M_mtime** Member der Dateistruktur Status ungleich NULL ist, die Attribute auch beeinträchtigt werden (die Zeit Stempel möglicherweise Nebeneffekte auf die Attribute ändern). Wenn Sie nur die Attribute der Datei ändern möchten, legen Sie zunächst die **M_mtime** Member der Struktur der Datei Status&0; (null) und anschließend einen Aufruf von `SetStatus`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&21;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]  
  
##  <a name="unlockrange"></a>CFile::UnlockRange  
 Hebt die Sperre eines Bereichs von Bytes in eine geöffnete Datei.  
  
```  
virtual void UnlockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Parameter  
 `dwPos`  
 Der Offset in Bytes vom Anfang des zu entsperrenden Bytebereichs.  
  
 `dwCount`  
 Die Anzahl der Bytes in der zu entsperrenden Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Beschreibung der [LockRange](#lockrange) Memberfunktion Details.  
  
> [!NOTE]
>  Diese Funktion ist nicht verfügbar für die `CMemFile`-Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#12;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="write"></a>CFile::Write  
 Schreibt Daten aus einem Puffer auf die Datei mit den `CFile` Objekt.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf den Benutzer bereitgestellte Puffer mit den Daten in die Datei geschrieben werden.  
  
 `nCount`  
 Die Anzahl der Bytes, die aus dem Puffer übertragen werden. Für Dateien, Textmodus Wagenrücklauf-Zeilenvorschub-Paare als einzelne Zeichen gezählt.  
  
### <a name="remarks"></a>Hinweise  
 **Schreiben von** eine Ausnahme als Reaktion auf verschiedene Faktoren, beispielsweise die voll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles Nr.&16;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]  
  
 Darüber hinaus finden Sie in den Beispielen für [CFile::CFile](#cfile) und [CFile::Open](#open).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)

