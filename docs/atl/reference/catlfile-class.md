---
title: Klasse CAtlFile | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5ba8aa0bc5544d8d541fecb87e2eb0108c2c5ebd
ms.lasthandoff: 02/24/2017

---
# <a name="catlfile-class"></a>CAtlFile-Klasse
Diese Klasse stellt einen einfacher Wrapper für die Windows-API-Datei verarbeitet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlFile : public CHandle
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::CAtlFile](#catlfile)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::Create](#create)|Rufen Sie diese Methode zum Erstellen oder Öffnen einer Datei.|  
|[CAtlFile::Flush](#flush)|Rufen Sie diese Methode, um den Puffer für die Datei löschen und dazu führen, dass alle gepufferte Daten in die Datei geschrieben werden.|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Rufen Sie diese Methode zum Abrufen der Ergebnisse eines überlappenden Vorgangs für die Datei.|  
|[CAtlFile::GetPosition](#getposition)|Rufen Sie diese Methode, um die aktuelle Dateiposition Zeiger aus der Datei zu erhalten.|  
|[CAtlFile::GetSize](#getsize)|Rufen Sie diese Methode, um die Größe in Bytes der Datei abrufen.|  
|[CAtlFile::LockRange](#lockrange)|Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse Zugriff zu sperren.|  
|[CAtlFile::Read](#read)|Rufen Sie diese Methode zum Lesen von Daten aus einer Datei, die an der Position des Zeigers Datei ab.|  
|[CAtlFile::Seek](#seek)|Rufen Sie diese Methode, um den Dateizeiger der Datei zu verschieben.|  
|[CAtlFile::SetSize](#setsize)|Rufen Sie diese Methode, um die Größe der Datei festgelegt.|  
|[CAtlFile::UnlockRange](#unlockrange)|Rufen Sie diese Methode, um einen Bereich der Datei zu entsperren.|  
|[CAtlFile::Write](#write)|Rufen Sie diese Methode, um Daten in der Datei, ab der Position des Zeigers Datei zu schreiben.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Klasse, wenn Dateibehandlung Anforderungen relativ einfach sind, aber mehr Abstraktion als die Windows-API bietet ohne MFC Abhängigkeiten erforderlich ist.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
##  <a name="catlfile"></a>CAtlFile::CAtlFile  
 Der Konstruktor.  
  
```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `file`  
 Das File-Objekt.  
  
 `hFile`  
 Das Dateihandle.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Der Kopierkonstruktor überträgt den Besitz des Dateihandles aus dem ursprünglichen `CAtlFile` Objekt, das das neu erstellte Objekt.  
  
##  <a name="create"></a>CAtlFile::Create  
 Rufen Sie diese Methode zum Erstellen oder Öffnen einer Datei.  
  
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
  
 `dwDesiredAccess`  
 Der gewünschte Zugriff. Finden Sie unter `dwDesiredAccess` in [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwShareMode`  
 Der Share-Modus. Finden Sie unter `dwShareMode` in **CreateFile**.  
  
 `dwCreationDisposition`  
 Die Disposition erstellen. Finden Sie unter `dwCreationDisposition` in **CreateFile**.  
  
 `dwFlagsAndAttributes`  
 Der Flags und Attribute. Finden Sie unter `dwFlagsAndAttributes` in **CreateFile**.  
  
 `lpsa`  
 Die Attribute für die Sicherheit. Finden Sie unter *LpSecurityAttributes* in **CreateFile**.  
  
 `hTemplateFile`  
 Die Datei der Vorlage. Finden Sie unter `hTemplateFile` in **CreateFile**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) erstellen oder öffnen die Datei.  
  
##  <a name="flush"></a>CAtlFile::Flush  
 Rufen Sie diese Methode, um den Puffer für die Datei löschen und dazu führen, dass alle gepufferte Daten in die Datei geschrieben werden.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439) gepufferte Daten auf die Datei zu speichern.  
  
##  <a name="getoverlappedresult"></a>CAtlFile::GetOverlappedResult  
 Rufen Sie diese Methode zum Abrufen der Ergebnisse eines überlappenden Vorgangs für die Datei.  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pOverlapped`  
 Die überlappende Struktur. Finden Sie unter `lpOverlapped` in [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *dwBytesTransferred*  
 Die Bytes übertragen. Finden Sie unter *LpNumberOfBytesTransferred* in `GetOverlappedResult`.  
  
 `bWait`  
 Die Wait-Option. Siehe auch `bWait` in `GetOverlappedResult`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) zum Abrufen der Ergebnisse eines überlappenden Vorgangs für die Datei.  
  
##  <a name="getposition"></a>CAtlFile::GetPosition  
 Rufen Sie diese Methode, um die aktuelle Dateiposition Zeiger zu erhalten.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Die Position in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) die aktuelle Dateiposition Zeiger abgerufen.  
  
##  <a name="getsize"></a>CAtlFile::GetSize  
 Rufen Sie diese Methode, um die Größe in Bytes der Datei abrufen.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nLen`  
 Die Anzahl der Bytes in der Datei.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [GetFileSize](http://msdn.microsoft.com/library/windows/desktop/aa364955) die Größe der Datei in Bytes ab.  
  
##  <a name="lockrange"></a>CAtlFile::LockRange  
 Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse Zugriff zu sperren.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Die Position in der Datei, in dem die Sperre beginnen soll.  
  
 `nCount`  
 Die Länge des Bytebereichs gesperrt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [Sperrdatei](http://msdn.microsoft.com/library/windows/desktop/aa365202) , einen Bereich in der Datei zu sperren. Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehrere Bereiche einer Datei sperren, jedoch keine überlappenden Bereiche sind zulässig. Wenn Sie eine Region entsperren, [CAtlFile::UnlockRange](#unlockrange), der Bytebereich muss entspricht exakt der Region, die zuvor gesperrt war. `LockRange`nicht zusammen benachbarte Bereiche; Wenn zwei gesperrte Bereiche nebeneinander angeordnet sind, müssen Sie jeweils einzeln entsperren.  
  
##  <a name="m_ptm"></a>CAtlFile::m_pTM  
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="read"></a>CAtlFile::Read  
 Rufen Sie diese Methode zum Lesen von Daten aus einer Datei, die an der Position des Zeigers Datei ab.  
  
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
 `pBuffer`  
 Zeiger auf den Puffer, der die Daten empfängt, die aus der Datei gelesen werden.  
  
 `nBufSize`  
 Die Puffergröße in Byte.  
  
 `nBytesRead`  
 Die Anzahl von gelesenen Bytes.  
  
 `pOverlapped`  
 Die überlappende Struktur. Finden Sie unter `lpOverlapped` in [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pfnCompletionRoutine`  
 Abschlussroutine beendet hat. Finden Sie unter *LpCompletionRoutine* in [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die ersten drei Formen [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467), das letzte [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) zum Lesen von Daten aus der Datei. Verwendung [CAtlFile::Seek](#seek) den Dateizeiger verschoben.  
  
##  <a name="seek"></a>CAtlFile::Seek  
 Rufen Sie diese Methode, um den Dateizeiger der Datei zu verschieben.  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nOffset`  
 Der Offset vom Ausgangspunkt vom `dwFrom`.  
  
 `dwFrom`  
 Der Anfangspunkt (FILE_BEGIN, FILE_CURRENT oder FILE_END).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) den Dateizeiger verschoben.  
  
##  <a name="setsize"></a>CAtlFile::SetSize  
 Rufen Sie diese Methode, um die Größe der Datei festgelegt.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nNewLen`  
 Die neue Länge der Datei in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) und [SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531) die Größe der Datei festlegen. Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.  
  
##  <a name="unlockrange"></a>CAtlFile::UnlockRange  
 Rufen Sie diese Methode, um einen Bereich der Datei zu entsperren.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Die Position in der Datei, wo das Entsperren beginnen soll.  
  
 `nCount`  
 Die Länge des Bytebereichs entsperrt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715) um einen Bereich der Datei zu entsperren.  
  
##  <a name="write"></a>CAtlFile::Write  
 Rufen Sie diese Methode, um Daten in der Datei, ab der Position des Zeigers Datei zu schreiben.  
  
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
 `pBuffer`  
 Der Puffer mit den Daten in die Datei geschrieben werden.  
  
 `nBufSize`  
 Die Anzahl der Bytes, die aus dem Puffer übertragen werden.  
  
 `pOverlapped`  
 Die überlappende Struktur. Finden Sie unter `lpOverlapped` in [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pfnCompletionRoutine`  
 Abschlussroutine beendet hat. Finden Sie unter *LpCompletionRoutine* in [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pnBytesWritten`  
 Die Bytes geschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die ersten drei Formen [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747), ruft der letzten [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) Daten in die Datei geschrieben. Verwendung [CAtlFile::Seek](#seek) den Dateizeiger verschoben.  
  
## <a name="see-also"></a>Siehe auch  
 [Marquee-Beispiel](../../visual-cpp-samples.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CHandle-Klasse](../../atl/reference/chandle-class.md)

