---
title: CAtlFile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afbb4600098591900491e7c1ec6f256bc58c26a4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220648"
---
# <a name="catlfile-class"></a>CAtlFile-Klasse
Diese Klasse stellt einen einfachen Wrapper für die Windows-Datei zur Behandlung von API.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlFile : public CHandle
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::CAtlFile](#catlfile)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::Create](#create)|Rufen Sie diese Methode zum Erstellen oder öffnen Sie eine Datei.|  
|[CAtlFile::Flush](#flush)|Rufen Sie diese Methode, um den Puffer für die Datei löschen, und dazu führen, dass alle gepufferte Daten in die Datei geschrieben werden.|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Rufen Sie diese Methode, um die Ergebnisse des einen überlappenden Vorgang in der Datei abzurufen.|  
|[CAtlFile::GetPosition](#getposition)|Rufen Sie diese Methode, um die aktuelle Zeigerposition für die Datei aus der Datei zu erhalten.|  
|[CAtlFile::GetSize](#getsize)|Rufen Sie diese Methode, um die Größe in Bytes der Datei abrufen.|  
|[CAtlFile::LockRange](#lockrange)|Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse darauf zugreifen zu sperren.|  
|[CAtlFile::Read](#read)|Rufen Sie diese Methode zum Lesen von Daten aus einer Datei, die an der durch den Dateizeiger angegebenen Position ab.|  
|[CAtlFile::Seek](#seek)|Rufen Sie diese Methode, um den Dateizeiger, der die Datei zu verschieben.|  
|[CAtlFile::SetSize](#setsize)|Rufen Sie diese Methode, um die Größe der Datei festgelegt.|  
|[CAtlFile::UnlockRange](#unlockrange)|Rufen Sie diese Methode, um einen Bereich der Datei zu entsperren.|  
|[CAtlFile::Write](#write)|Rufen Sie diese Methode zum Schreiben von Daten in der Datei, die an der durch den Dateizeiger angegebenen Position ab.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Klasse aus, wenn Dateibehandlung Anforderungen relativ einfach sind, aber weitere Abstraktion, die als die Windows-API bietet erforderlich, ist ohne Abhängigkeiten von MFC.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
##  <a name="catlfile"></a>  CAtlFile::CAtlFile  
 Der Konstruktor.  
  
```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *datei*  
 Das Objekt "Datei".  
  
 *hFile*  
 Das Dateihandle.  
  
 *pTM*  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Die Copy-Konstruktor überträgt den Besitz des Dateihandles aus der ursprünglichen `CAtlFile` Objekt, das das neu erstellte Objekt.  
  
##  <a name="create"></a>  CAtlFile::Create  
 Rufen Sie diese Methode zum Erstellen oder öffnen Sie eine Datei.  
  
```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *szFilename*  
 Der Dateiname.  
  
 *dwDesiredAccess*  
 Der gewünschte Zugriff. Finden Sie unter *DwDesiredAccess* in [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) im Windows SDK.  
  
 *dwShareMode*  
 Der Freigabemodus. Finden Sie unter *DwShareMode* in `CreateFile`.  
  
 *dwCreationDisposition*  
 Die Erstellungsdisposition. Finden Sie unter *DwCreationDisposition* in `CreateFile`.  
  
 *dwFlagsAndAttributes*  
 Die Flags und Attribute. Finden Sie unter *DwFlagsAndAttributes* in `CreateFile`.  
  
 *lpsa*  
 Die Attribute für die Sicherheit. Finden Sie unter *LpSecurityAttributes* in `CreateFile`.  
  
 *hTemplateFile*  
 Die Vorlagendatei. Finden Sie unter *hTemplateFile* in `CreateFile`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) erstellen oder öffnen Sie die Datei.  
  
##  <a name="flush"></a>  CAtlFile::Flush  
 Rufen Sie diese Methode, um den Puffer für die Datei löschen, und dazu führen, dass alle gepufferte Daten in die Datei geschrieben werden.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [FlushFileBuffers](/windows/desktop/api/fileapi/nf-fileapi-flushfilebuffers) gepufferte Daten auf dem die Datei zu speichern.  
  
##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult  
 Rufen Sie diese Methode, um die Ergebnisse des einen überlappenden Vorgang in der Datei abzurufen.  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *"pOverlapped"*  
 Die überlappende Struktur. Finden Sie unter *LpOverlapped* in [GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) im Windows SDK.  
  
 *dwBytesTransferred*  
 Die Bytes übertragen. Finden Sie unter *LpNumberOfBytesTransferred* in `GetOverlappedResult`.  
  
 *bWait*  
 Die Option "Abfragewartezeit". Finden Sie unter *bWait* in `GetOverlappedResult`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) zum Abrufen der Ergebnisse eines überlappenden Vorgangs auf die Datei.  
  
##  <a name="getposition"></a>  CAtlFile::GetPosition  
 Rufen Sie diese Methode, um die aktuelle Zeigerposition für die Datei zu erhalten.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nPos*  
 Die Position in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) um die aktuelle Zeigerposition für die Datei zu erhalten.  
  
##  <a name="getsize"></a>  CAtlFile::GetSize  
 Rufen Sie diese Methode, um die Größe in Bytes der Datei abrufen.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nLen*  
 Die Anzahl der Bytes in der Datei.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [' GetFileSize '](/windows/desktop/api/fileapi/nf-fileapi-getfilesize) zum Abrufen der Größe der Datei in Bytes.  
  
##  <a name="lockrange"></a>  CAtlFile::LockRange  
 Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse darauf zugreifen zu sperren.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nPos*  
 Die Position in der Datei, in dem die Sperre begonnen werden soll.  
  
 *nCount*  
 Die Länge des Bytebereichs gesperrt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [Sperrdatei](/windows/desktop/api/fileapi/nf-fileapi-lockfile) , einen Bereich in der Datei zu sperren. Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als einer Region in einer Datei sperren, aber keine sich überschneidenden Bereiche sind zulässig. Wenn Sie eine Region entsperrt haben, [CAtlFile::UnlockRange](#unlockrange), der Bytebereich muss genau in der Region, die zuvor gesperrt wurde, entsprechen. `LockRange` benachbarte Bereiche zusammen nicht; Wenn zwei gesperrte Bereiche aneinandergrenzen, müssen Sie jeweils separat entsperren.  
  
##  <a name="m_ptm"></a>  CAtlFile::m_pTM  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="read"></a>  CAtlFile::Read  
 Rufen Sie diese Methode zum Lesen von Daten aus einer Datei, die an der durch den Dateizeiger angegebenen Position ab.  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pBuffer*  
 Zeiger auf den Puffer, der die Daten erhält, die aus der Datei gelesen werden.  
  
 *nBufSize*  
 Die Puffergröße in Byte.  
  
 *nBytesRead*  
 Die Anzahl von gelesenen Bytes.  
  
 *"pOverlapped"*  
 Die überlappende Struktur. Finden Sie unter *LpOverlapped* in [ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile) im Windows SDK.  
  
 *pfnCompletionRoutine*  
 Der Abschlussroutine. Finden Sie unter *LpCompletionRoutine* in [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die ersten drei Formulare [ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile), den letzten [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) zum Lesen von Daten aus der Datei. Verwendung [CAtlFile::Seek](#seek) den Dateizeiger verschoben.  
  
##  <a name="seek"></a>  CAtlFile::Seek  
 Rufen Sie diese Methode, um den Dateizeiger, der die Datei zu verschieben.  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nOffset*  
 Der Offset vom vom Ausgangspunkt *DwFrom*.  
  
 *dwFrom*  
 Der Anfangspunkt (FILE_BEGIN, FILE_CURRENT oder FILE_END).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) den Dateizeiger verschoben.  
  
##  <a name="setsize"></a>  CAtlFile::SetSize  
 Rufen Sie diese Methode, um die Größe der Datei festgelegt.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nNewLen*  
 Die neue Länge der Datei in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) und [SetEndOfFile](/windows/desktop/api/fileapi/nf-fileapi-setendoffile) die Größe der Datei festgelegt. Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.  
  
##  <a name="unlockrange"></a>  CAtlFile::UnlockRange  
 Rufen Sie diese Methode, um einen Bereich der Datei zu entsperren.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nPos*  
 Die Position in der Datei, in dem das Entsperren begonnen werden soll.  
  
 *nCount*  
 Die Länge des Bytebereichs entsperrt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [UnlockFile](/windows/desktop/api/fileapi/nf-fileapi-unlockfile) um einen Bereich der Datei zu entsperren.  
  
##  <a name="write"></a>  CAtlFile::Write  
 Rufen Sie diese Methode zum Schreiben von Daten in der Datei, die an der durch den Dateizeiger angegebenen Position ab.  
  
```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pBuffer*  
 Der Puffer mit Daten, die in die Datei geschrieben werden.  
  
 *nBufSize*  
 Die Anzahl der Bytes, aus dem Puffer übertragen werden sollen.  
  
 *"pOverlapped"*  
 Die überlappende Struktur. Finden Sie unter *LpOverlapped* in [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) im Windows SDK.  
  
 *pfnCompletionRoutine*  
 Der Abschlussroutine. Finden Sie unter *LpCompletionRoutine* in [WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) im Windows SDK.  
  
 *pnBytesWritten*  
 Die Bytes geschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die ersten drei Formulare [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile), die letzte Aufrufe [WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) zum Schreiben von Daten in die Datei. Verwendung [CAtlFile::Seek](#seek) den Dateizeiger verschoben.  
  
## <a name="see-also"></a>Siehe auch  
 [Marquee-Beispiel](../../visual-cpp-samples.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CHandle-Klasse](../../atl/reference/chandle-class.md)
