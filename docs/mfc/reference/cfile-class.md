---
title: CFile-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
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
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4db8a7ee97c414a7775df393d419c7d12d61cdbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[CFile::CFile](#cfile)|Erstellt eine `CFile` Objekt aus einem Handle Pfad- oder Dateiname.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFile::Abort](#abort)|Schließt eine Datei, die alle Warnungen und Fehler ignorieren.|  
|[CFile::Close](#close)|Eine Datei schließt und löscht das Objekt.|  
|[CFile::Duplicate](#duplicate)|Erstellt ein doppeltes Objekt basierend auf diese Datei an.|  
|[CFile::Flush](#flush)|Leert alle Daten noch geschrieben werden.|  
|[CFile::GetFileName](#getfilename)|Ruft den Dateinamen der ausgewählten Datei ab.|  
|[CFile::GetFilePath](#getfilepath)|Ruft den vollständigen Dateipfad der ausgewählten Datei ab.|  
|[CFile::GetFileTitle](#getfiletitle)|Ruft den Titel der ausgewählten Datei ab.|  
|[CFile::GetLength](#getlength)|Ruft die Länge der Datei ab.|  
|[CFile::GetPosition](#getposition)|Ruft die aktuelle Dateizeiger ab.|  
|[CFile:: GetStatus](#getstatus)|Ruft den Status der geöffneten Datei oder in der statischen Version ab, der Status der angegebenen Datei (statische virtuelle Funktion) abgerufen.|  
|[CFile::LockRange](#lockrange)|Sperren einen Bereich von Bytes in einer Datei.|  
|[CFile::Open](#open)|Sicher öffnet eine Datei mit einer Option zum Testen auf Fehler.|  
|[CFile:: Read](#read)|Lesevorgänge (gepufferten) Daten aus einer Datei an der aktuellen Dateiposition.|  
|[CFile::Remove](#remove)|Löscht die angegebene Datei (statische Funktion).|  
|[CFile::Rename](#rename)|Benennt die angegebene Datei (statische Funktion).|  
|[CFile::Seek](#seek)|Positioniert den Zeiger auf den aktuellen Datei an.|  
|[CFile::SeekToBegin](#seektobegin)|Positioniert den aktuellen Dateizeiger am Anfang der Datei an.|  
|[CFile::SeekToEnd](#seektoend)|Positioniert den aktuellen Dateizeiger am Ende der Datei an.|  
|[CFile::SetFilePath](#setfilepath)|Legt den vollständigen Dateipfad der ausgewählten Datei an.|  
|[CFile::SetLength](#setlength)|Ändert die Länge der Datei an.|  
|[CFile::SetStatus](#setstatus)|Setzt den Status der angegebenen Datei (statische virtuelle Funktion).|  
|[CFile::UnlockRange](#unlockrange)|Entsperren Sie einen Bereich von Bytes in einer Datei ein.|  
|[CFile::Write](#write)|Schreibvorgänge (gepufferten) Daten in einer Datei an die aktuelle Dateiposition.|  
  
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
 Es bietet direkt nicht zwischengespeicherten, binäre Datenträger e/a-Dienste und indirekt Textdateien und Speicher-Dateien über den abgeleiteten Klassen unterstützt. `CFile`funktioniert in Verbindung mit der `CArchive` Klasse, um die Serialisierung der Microsoft Foundation Class-Objekte unterstützt.  
  
 Die hierarchische Beziehung zwischen dieser Klasse und abgeleitete Klassen können Sie das Programm, das alle File-Objekten über die polymorphe verarbeitet werden `CFile` Schnittstelle. Eine Arbeitsspeicherdatei verhält sich z. B. wie eine Datenträgerdatei.  
  
 Verwendung `CFile` und abgeleitete Klassen für allgemeine Datenträger-e/a. Verwendung `ofstream` oder andere Microsoft-Iostream-Klassen für formatierten Text an eine Datenträgerdatei gesendet.  
  
 In der Regel wird eine Datenträgerdatei automatisch geöffnet wird `CFile` Konstruktion und Zerstörung geschlossen. Statische Member-Funktionen können Sie des Status einer Datei abzufragen, ohne die Datei zu öffnen.  
  
 Weitere Informationen zur Verwendung von `CFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="abort"></a>CFile::Abort  
 Schließt die Datei, die diesem Objekt zugeordnet, und die Datei nicht zum Lesen oder Schreiben verfügbar macht.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Datei nicht vor dem Löschen des Objekts geschlossen haben, wird es von der Destruktor geschlossen.  
  
 Beim Verarbeiten von Ausnahmen, `CFile::Abort` unterscheidet sich von `CFile::Close` in zwei wichtigen Aspekten. Zuerst die **Abort** Funktion nicht löst eine Ausnahme auf Fehler, da Fehler, indem ignoriert werden **Abort**. Zweitens **Abort** nicht **ASSERT** Wenn die Datei nicht geöffnet wurde oder wurde bereits geschlossen.  
  
 Bei Verwendung **neue** Zuweisen der `CFile` Objekt auf dem Heap, und Sie sie löschen müssen, nach dem Schließen der Datei. **Abort** legt `m_hFile` auf `CFile::hFileNull`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]  
  
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
|`CFile::modeCreate`|Erstellt eine neue Datei, wenn keine Datei existiert.; Wenn die Datei bereits vorhanden ist, [CFileException](../../mfc/reference/cfileexception-class.md) ausgelöst wird.|  
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
  
 Der Standardkonstruktor initialisiert Member, hängt jedoch keine Datei an das `CFile`-Objekt an. Nach der Verwendung dieses Konstruktors, der [CFile::Open](#open) Methode, um eine Datei öffnen, und fügen Sie es auf die `CFile` Objekt.  
  
 Der Konstruktor mit einem Parameter initialisiert Member und hängt eine vorhandene Datei an das `CFile`-Objekt an.  
  
 Der Konstruktor mit zwei Parametern initialisiert Member und versucht, die angegebene Datei zu öffnen. Wenn der Konstruktor die angegebene Datei erfolgreich öffnet, wird die Datei an das `CFile`-Objekt angehängt; anderenfalls löst der Konstruktor einen Zeiger auf ein `CInvalidArgException`-Objekt aus. Weitere Informationen über das Behandeln von Ausnahmen finden Sie unter [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
 Wenn ein `CFile`-Objekt eine angegebene Datei erfolgreich öffnet, wird diese Datei automatisch geschlossen, wenn das `CFile`-Objekt zerstört wird; anderenfalls müssen Sie die Datei explizit schließen, wenn sie nicht mehr an das `CFile`-Objekt angehängt ist.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht die Verwendung einer `CFile`.  
  
 [!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]  
  
##  <a name="close"></a>CFile::Close  
 Schließt die Datei, die diesem Objekt zugeordnet, und die Datei nicht zum Lesen oder Schreiben verfügbar macht.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Datei nicht vor dem Löschen des Objekts geschlossen haben, wird es von der Destruktor geschlossen.  
  
 Bei Verwendung **neue** Zuweisen der `CFile` Objekt auf dem Heap, und Sie sie löschen müssen, nach dem Schließen der Datei. **Schließen** legt `m_hFile` auf `CFile::hFileNull`.  
  
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
 Dies ist gleichbedeutend mit der C-Laufzeitbibliotheksfunktion `_dup`.  
  
##  <a name="flush"></a>CFile::Flush  
 Erzwingt, dass alle verbleibenden Dateipuffers in die Datei geschrieben werden sollen.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Verwendung von `Flush` garantiert nicht geleert `CArchive` Puffer. Wenn Sie ein Archiv verwenden, rufen Sie [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) erste.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFile::SetFilePath](#setfilepath).  
  
##  <a name="getfilename"></a>CFile::GetFileName  
 Rufen Sie diese Memberfunktion um den Namen einer angegebenen Datei abzurufen.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. beim Aufruf `GetFileName` zum Generieren einer Nachricht an den Benutzer über die Datei `c:\windows\write\myfile.wri`, den Dateinamen `myfile.wri`, zurückgegeben.  
  
 Rufen Sie den vollständigen Pfad der Datei, einschließlich des Namens zurückzugebenden [GetFilePath](#getfilepath). Den Titel der Datei zurückgegeben ( `myfile`), rufen Sie [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment wird das SYSTEM geöffnet. INI-Datei in Ihrem WINDOWS-Verzeichnis. Wenn gefunden, im Beispiel wird der Name und der Pfad und der Titel drucken möchten wie in der Ausgabe dargestellt:  
  
 [!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]  
  
##  <a name="getfilepath"></a>CFile::GetFilePath  
 Rufen Sie diese Memberfunktion um den vollständigen Pfad einer angegebenen Datei abgerufen.  
  
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
 Rufen Sie diese Memberfunktion zum Abrufen des Datei Titels (den Anzeigenamen) für die Datei an.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel des zugrunde liegenden Datei.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) um den Titel der Datei abzurufen. Bei erfolgreicher Ausführung gibt die Methode die Zeichenfolge, die das System verwenden würden, um den Dateinamen für den Benutzer anzuzeigen zurück. Andernfalls, ruft die Methode [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) der Dateiname (einschließlich der Dateierweiterung) der zugrunde liegenden Datei abgerufen. Aus diesem Grund wird die Dateierweiterung nicht immer in der zurückgegebenen Datei Titelzeichenfolge enthalten sein. Weitere Informationen finden Sie unter [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) und [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) im Windows SDK.  
  
 Rufen Sie den vollständigen Pfad der Datei, einschließlich des Namens zurückzugebenden [GetFilePath](#getfilepath). Nur der Name der Datei rufen Sie zum Zurückgeben [GetFileName](#getfilename).  
  
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
 [!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]  
  
##  <a name="getposition"></a>CFile::GetPosition  
 Ruft den aktuellen Wert des Zeigers Datei, die bei nachfolgenden Funktionsaufrufen verwendet werden können `Seek`.  
  
```  
virtual ULONGLONG GetPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Dateizeiger.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]  
  
##  <a name="getstatus"></a>CFile:: GetStatus  
 Diese Methode ruft Statusinformationen, die im Zusammenhang mit einem bestimmten `CFile` Objektinstanz oder einen angegebenen Dateipfad.  
  
```  
BOOL GetStatus(CFileStatus& rStatus) const;  
  
static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,  
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rStatus`  
 Ein Verweis auf eine vom Benutzer bereitgestellte **CFileStatus** Struktur, die die Statusinformationen zu erhalten. Die **CFileStatus** Struktur enthält die folgenden Felder:  
  
- **CTime M_ctime** Datum und Uhrzeit die Datei erstellt wurde.  
  
- **CTime M_mtime** Datum und Uhrzeit der letzten der Datei Änderung.  
  
- **CTime M_atime** Datum und Uhrzeit auf die Datei zuletzt zugegriffen wurde, zum Lesen.  
  
- **ULONGLONG M_size** die logische Größe der Datei in Bytes, so wie durch den Befehl "DIR" gemeldet.  
  
- **BYTE-M_attribute** das Attribut Byte der Datei.  
  
- **M_szFullName [_MAX_PATH] char** den absoluten Dateinamen in den Windows-Zeichensatz.  
  
 `lpszFileName`  
 Eine Zeichenfolge in das Windows-Zeichen werden also den Pfad zu der gewünschten Datei fest. Der Pfad kann relativ oder absolut sein, oder es kann ein Name des Netzwerkpfads enthalten.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist die Statusinformationen für die angegebene Datei erfolgreich abgerufen wurde; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Die Version nicht statische **GetStatus** ruft Statusinformationen der geöffneten Datei zugeordneten ab der angegebenen `CFile` Objekt.  Die statische Version des **GetStatus** erhält den Status der Datei aus einem Pfad angegebene Datei, ohne tatsächlich Öffnen der Datei. Dies ist hilfreich für das Vorhandensein und die Zugriffsrechte einer Datei zu testen.  
  
 Die **M_attribute** Mitglied der **CFileStatus** Struktur bezieht sich auf die Datei-Attribut. Die `CFile` -Klasse stellt die **Attribut** Enumeration zu geben, damit Dateiattribute symbolisch angegeben werden können:  
  
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
  
##  <a name="hfilenull"></a>CFile::hFileNull  
 Bestimmt das Vorhandensein einer gültigen Dateihandle für die `CFile` Objekt.  
  
```  
static AFX_DATA const HANDLE hFileNull;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Konstante wird verwendet, um festzustellen, wo die `CFile` Objekt verfügt über eine gültige Dateihandle.  
  
 Das folgende Beispiel zeigt diesen Vorgang:  
  
 [!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]  
  
##  <a name="lockrange"></a>CFile::LockRange  
 Sperren einen Bereich von Bytes in einer geöffneten Datei, die eine Ausnahme auszulösen, wenn die Datei bereits gesperrt ist.  
  
```  
virtual void LockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Parameter  
 `dwPos`  
 Der Byte-Offset vom Anfang des zu sperrenden Bytebereichs.  
  
 `dwCount`  
 Die Anzahl der Bytes in der zu sperrenden Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als ein Bereich einer Datei sperren, aber keine überlappenden Bereiche sind zulässig.  
  
 Wenn Sie die Region entsperrt werden, mithilfe der `UnlockRange` Memberfunktion der Bytebereich muss genau in der Region, die zuvor gesperrt war entsprechen. Die `LockRange` Funktion nicht angrenzende Bereichen zusammen, wenn zwei gesperrte Bereiche nebeneinander angeordnet sind, müssen Sie jede Region separat entsperren.  
  
> [!NOTE]
>  Diese Funktion ist nicht verfügbar für die `CMemFile`-Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="m_hfile"></a>CFile::m_hFile  
 Enthält das Betriebssystem-Dateihandle für eine geöffnete Datei.  
  
```  
HANDLE m_hFile;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_hFile`ist eine öffentliche Variable des Typs **"uint"**. Er enthält `CFile::hFileNull` (eine leere Datei Betriebssystem-systemunabhängig Indicator), wenn das Handle nicht zugewiesen wurden.  
  
 Verwenden von `m_hFile` wird nicht empfohlen, da die abgeleitete Klasse Bedeutung für das Element abhängig ist. `m_hFile`einen öffentlichen Member der Einfachheit halber bei der Unterstützung von nicht polymorphen Verwendung der Klasse wird hergestellt werden.  
  
##  <a name="m_ptm"></a>CFile::m_pTM  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="open"></a>CFile::Open  
 Überladen. **Open** dient zur Verwendung mit der standardmäßigen `CFile` Konstruktor.  
  
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
 Eine Zeichenfolge, die den Pfad zu der gewünschten Datei ist. Der Pfad kann relativ, absolut oder den Namen eines Netzwerks (UNC) sein.  
  
 `nOpenFlags`  
 Ein **"uint"** , definiert die Datei freigeben und Zugriffsmodus. Es gibt die zu ergreifende Maßnahme beim Öffnen der Datei an. Sie können Optionen kombinieren, mit dem bitweisen OR-( **&#124;** ) Operator. Eine Access-Berechtigung und eine Freigabe Option sind erforderlich. die **ModeCreate** und **ModeNoInherit** Modi sind optional. Finden Sie unter der [CFile](#cfile) eine Liste der Optionen für den Konstruktor.  
  
 `pError`  
 Ein Zeiger auf ein vorhandenes Datei-Ausnahme-Objekt, das den Status eines fehlgeschlagenen Vorgangs erhält.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Öffnen erfolgreich war; andernfalls 0. Die `pError` Parameter ist nur sinnvoll, wenn 0 zurückgegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Die zwei Funktionen bilden einen "sicheren"-Methode zum Öffnen einer Datei, in dem ein Fehler für eine normale, erwartete Bedingung ist.  
  
 Während der `CFile` Konstruktors löst eine Ausnahme in einem Fehlerzustand **öffnen** zurück **"false"** für fehlerbedingungen. **Open** können weiterhin initialisieren eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt, das den Fehler jedoch zu beschreiben. Falls Sie nicht angeben der `pError` Parameter, oder wenn Sie übergeben **NULL** für `pError`, **öffnen** zurück **"false"** und löst eine `CFileException`. Wenn Sie einen Zeiger auf eine vorhandene übergeben `CFileException`, und **öffnen** prüfpunkterstellung einen Fehler erkennt, die Funktion wird mit Informationen gefüllt, die den Fehler beschreibt. Keine Groß-/Kleinschreibung wird **öffnen** lösen eine Ausnahme aus.  
  
 Die folgende Tabelle beschreibt die möglichen Ergebnisse **öffnen**.  
  
|`pError`|Fehler:|Rückgabewert|CFileException Inhalt|  
|--------------|------------------------|------------------|----------------------------|  
|**NULL**|Nein|**"TRUE"**|n/v|  
|Zeiger auf`CFileException`|Nein|**"TRUE"**|unverändert|  
|**NULL**|Ja|**"FALSE"**|n/v|  
|Zeiger auf`CFileException`|Ja|**"FALSE"**|initialisiert werden, um Fehler zu beschreiben.|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]  
  
##  <a name="operator_handle"></a>CFile::operator HANDLE  
 Verwenden Sie diesen Operator übergeben Sie ein Handle für ein `CFile` -Objekt an Funktionen wie [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) und [GetFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724320) erwarten, die eine `HANDLE`.  
  
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
 Zeiger auf den vom Benutzer bereitgestellte Puffer, die die Daten empfangen, die aus der Datei gelesen werden.  
  
 `nCount`  
 Die maximale Anzahl von Bytes aus der Datei gelesen werden. Für Textmodus Dateien, Carriage Return-Zeilenvorschub-Paare werden als einzelne Zeichen gezählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in den Puffer übertrageben Bytes. Beachten Sie, dass für alle `CFile` Klassen, ist der Rückgabewert möglicherweise kleiner als `nCount` , wenn das Ende der Datei erreicht wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CFile::Open](#open).  
  
##  <a name="remove"></a>CFile::Remove  
 Diese statische Funktion löscht den vom Pfad angegebenen Datei.  
  
```  
static void PASCAL Remove(
    LPCTSTR lpszFileName, 
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zu der gewünschten Datei ist. Der Pfad kann relativ oder absolut sein und darf einen Netzwerknamen.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Es wird ein Verzeichnis nicht zu entfernen.  
  
 Die **entfernen** Memberfunktion löst eine Ausnahme aus, wenn die verbundenen Datei geöffnet ist oder wenn die Datei kann nicht entfernt werden. Dies entspricht dem DEL-Befehl.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]  
  
##  <a name="rename"></a>CFile::Rename  
 Diese statische Funktion benennt die angegebene Datei.  
  
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
 Verzeichnisse können nicht umbenannt werden. Dies entspricht dem REN-Befehl.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]  
  
##  <a name="seek"></a>CFile::Seek  
 Verschiebt den Dateizeiger in einer geöffneten Datei.  
  
```  
virtual ULONGLONG Seek(
LONGLONG lOff,  
UINT nFrom);
```  
  
### <a name="parameters"></a>Parameter  
 `lOff`  
 Die Anzahl der Bytes, den Dateizeiger zu verschieben. Positive Werte verschieben den Dateizeiger am Ende der Datei; negative Werte bewegen den Dateizeiger für den Anfang der Datei.  
  
 `nFrom`  
 Die Position zu suchende aus. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des Dateizeigers, wenn die Methode erfolgreich ausgeführt wurde; Andernfalls ist der Rückgabewert nicht definiert und einen Zeiger auf eine `CFileException` Ausnahme wird ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nFrom` Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CFile::begin`|Die Suche vom Anfang der Datei.|  
|`CFile::current`|Suchen von der aktuellen Position des Dateizeigers.|  
|`CFile::end`|Die Suche vom Ende der Datei.|  
  
 Wenn eine Datei geöffnet wird, wird der Dateizeiger bei 0 zu Beginn der Datei positioniert.  
  
 Sie können den Dateizeiger an eine Position hinter dem Ende einer Datei festlegen. Wenn Sie so vorgehen, erhöht die Größe der Datei nicht, bis Sie die Datei geschrieben.  
  
 Der Ausnahmehandler für diese Methode muss das Ausnahmeobjekt löschen, nachdem die Ausnahme verarbeitet wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]  
  
##  <a name="seektobegin"></a>CFile::SeekToBegin  
 Legt den Wert des Dateizeigers auf den Anfang der Datei fest.  
  
```  
void SeekToBegin();
```  
  
### <a name="remarks"></a>Hinweise  
 `SeekToBegin()` entspricht `Seek( 0L, CFile::begin )`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="seektoend"></a>CFile::SeekToEnd  
 Legt den Wert des Dateizeigers auf dem logischen Ende der Datei fest.  
  
```  
ULONGLONG SeekToEnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Datei in Byte.  
  
### <a name="remarks"></a>Hinweise  
 `SeekToEnd()` entspricht `CFile::Seek( 0L, CFile::end )`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="setfilepath"></a>CFile::SetFilePath  
 Rufen Sie diese Funktion, um den Pfad der Datei angeben. Angenommen, wenn der Pfad einer Datei nicht verfügbar ist eine [CFile](../../mfc/reference/cfile-class.md) Objekt erstellt wurde, rufen Sie `SetFilePath` ihn zur Verfügung stellen.  
  
```  
virtual void SetFilePath(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewName`  
 Zeiger auf eine Zeichenfolge, die den neuen Pfad angeben.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> `SetFilePath`nicht öffnen Sie die Datei oder erstellen Sie die Datei; er einfach ordnet die `CFile` Objekt mit einem Pfadnamen, die dann verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]  
  
##  <a name="setlength"></a>CFile::SetLength  
 Mit dieser Funktion wird zum Ändern der Länge der Datei.  
  
```  
virtual void SetLength(ULONGLONG dwNewLen);
```  
  
### <a name="parameters"></a>Parameter  
 `dwNewLen`  
 Die gewünschte Länge der Datei in Bytes. Dieser Wert kann größer oder kleiner als die aktuelle Länge der Datei sein. Die Datei werden erweitert oder je nach Bedarf abgeschnitten.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Mit `CMemFile`, konnte diese Funktion löst einen `CMemoryException` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]  
  
##  <a name="setstatus"></a>CFile::SetStatus  
 Legt den Status der Datei zugeordneten Speicherort dieser Datei fest.  
  
```  
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,  
    const CFileStatus& status,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zu der gewünschten Datei ist. Der Pfad kann relativ oder absolut sein und darf einen Netzwerknamen.  
  
 *status*  
 Der Puffer mit den neuen Statusinformationen. Rufen Sie die **GetStatus** Memberfunktion prefill der **CFileStatus** -Struktur mit den aktuellen Werten, und ändern Sie dann nach Bedarf. Wenn ein Wert 0 ist, wird das entsprechende Element der Status nicht aktualisiert. Finden Sie unter der [GetStatus](#getstatus) Memberfunktion, die eine Beschreibung der **CFileStatus** Struktur.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie zum Festlegen der Uhrzeit der **M_mtime** Feld *Status*.  
  
 Bitte beachten Sie, dass bei einem Aufruf von `SetStatus` bei einem Versuch, die nur die Attribute der Datei ändern und die **M_mtime** Mitglied von der Dateistruktur des Status ist ungleich NULL, die Attribute können auch beeinträchtigt sein (ändern den Zeitstempel Nebeneffekte auf den Attributen möglicherweise). Wenn Sie nur die Attribute der Datei ändern möchten, legen Sie zuerst die **M_mtime** Mitglied der Dateistruktur des Status auf 0 (null), und stellen Sie dann einen Aufruf von `SetStatus`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]  
  
##  <a name="unlockrange"></a>CFile::UnlockRange  
 Gibt einen Bereich von Bytes in einer geöffneten Datei frei.  
  
```  
virtual void UnlockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Parameter  
 `dwPos`  
 Der Byte-Offset vom Anfang des zu entsperrenden Bytebereichs.  
  
 `dwCount`  
 Die Anzahl der Bytes in der zu entsperrenden Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Siehe dazu die Beschreibung der [LockRange](#lockrange) Memberfunktion für Details.  
  
> [!NOTE]
>  Diese Funktion ist nicht verfügbar für die `CMemFile`-Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="write"></a>CFile::Write  
 Schreibt Daten aus einem Puffer, an die zugeordnete Datei die `CFile` Objekt.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf den vom Benutzer bereitgestellte Puffer mit den Daten in die Datei geschrieben werden sollen.  
  
 `nCount`  
 Die Anzahl der Bytes, die aus dem Puffer übertragen werden. Für Textmodus Dateien, Carriage Return-Zeilenvorschub-Paare werden als einzelne Zeichen gezählt.  
  
### <a name="remarks"></a>Hinweise  
 **Schreiben von** löst eine Ausnahme aus, in Reaktion auf verschiedene Bedingungen, einschließlich der Datenträger voll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]  
  
 Darüber hinaus finden Sie unter den Beispielen für [CFile::CFile](#cfile) und [CFile::Open](#open).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)
