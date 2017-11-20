---
title: CAtlFile Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 557c0451f0c33e13a8fb572f77c387b43daea6f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="catlfile-class"></a>CAtlFile-Klasse
Diese Klasse bietet einen funktionsarmen Wrapper um die Windows-Datei-API-Behandlung.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CAtlFile::Create](#create)|Rufen Sie diese Methode zum Erstellen oder öffnen Sie eine Datei.|  
|[CAtlFile::Flush](#flush)|Rufen Sie diese Methode, um den Puffer für die Datei löschen und dazu führen, dass alle gepufferte Daten in die Datei geschrieben werden sollen.|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Rufen Sie diese Methode, um die Ergebnisse eines überlappenden Vorgangs für die Datei zu erhalten.|  
|[CAtlFile::GetPosition](#getposition)|Rufen Sie diese Methode, um die aktuelle Zeigerposition für die Datei aus der Datei zu erhalten.|  
|[CAtlFile::GetSize](#getsize)|Rufen Sie diese Methode, um die Größe in Bytes der Datei abrufen.|  
|[CAtlFile::LockRange](#lockrange)|Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse zugegriffen wird zu sperren.|  
|[CAtlFile::Read](#read)|Rufen Sie diese Methode zum Lesen von Daten aus einer Datei, ab der Position des Dateizeigers erkennbar.|  
|[CAtlFile::Seek](#seek)|Rufen Sie diese Methode, um den Dateizeiger der Datei zu verschieben.|  
|[CAtlFile::SetSize](#setsize)|Rufen Sie diese Methode, um die Größe der Datei festgelegt.|  
|[CAtlFile::UnlockRange](#unlockrange)|Rufen Sie diese Methode, um einen Bereich der Datei zu entsperren.|  
|[CAtlFile::Write](#write)|Rufen Sie diese Methode zum Schreiben von Daten in der Datei, ab der Position des Dateizeigers erkennbar.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Klasse, wenn Dateibehandlung Anforderungen relativ einfach sind, aber weitere Abstraktion als die Windows-API bietet ohne MFC Abhängigkeiten erforderlich ist.  
  
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
 Das Objekt "Datei".  
  
 `hFile`  
 Das Dateihandle.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Der Kopierkonstruktor überträgt den Besitz des Dateihandles aus der ursprünglichen `CAtlFile` Objekt, das das neu erstellte Objekt.  
  
##  <a name="create"></a>CAtlFile::Create  
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
  
 `dwDesiredAccess`  
 Der gewünschte Zugriff. Finden Sie unter `dwDesiredAccess` in [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) im Windows SDK.  
  
 `dwShareMode`  
 Der Freigabemodus. Finden Sie unter `dwShareMode` in **CreateFile**.  
  
 `dwCreationDisposition`  
 Die Disposition erstellen. Finden Sie unter `dwCreationDisposition` in **CreateFile**.  
  
 `dwFlagsAndAttributes`  
 Die Flags und Attribute. Finden Sie unter `dwFlagsAndAttributes` in **CreateFile**.  
  
 `lpsa`  
 Die Sicherheitsattribute. Finden Sie unter *LpSecurityAttributes* in **CreateFile**.  
  
 `hTemplateFile`  
 Die Vorlagendatei. Finden Sie unter `hTemplateFile` in **CreateFile**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) erstellen oder öffnen Sie die Datei.  
  
##  <a name="flush"></a>CAtlFile::Flush  
 Rufen Sie diese Methode, um den Puffer für die Datei löschen und dazu führen, dass alle gepufferte Daten in die Datei geschrieben werden sollen.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439) gepufferte Daten in die Datei geleert.  
  
##  <a name="getoverlappedresult"></a>CAtlFile::GetOverlappedResult  
 Rufen Sie diese Methode, um die Ergebnisse eines überlappenden Vorgangs für die Datei zu erhalten.  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pOverlapped`  
 Die überlappende Struktur. Finden Sie unter `lpOverlapped` in [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) im Windows SDK.  
  
 *dwBytesTransferred*  
 Die Bytes übertragen. Finden Sie unter *LpNumberOfBytesTransferred* in `GetOverlappedResult`.  
  
 `bWait`  
 Die Abfragewartezeit (Option). Siehe auch `bWait` in `GetOverlappedResult`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) um die Ergebnisse eines überlappenden Vorgangs für die Datei zu erhalten.  
  
##  <a name="getposition"></a>CAtlFile::GetPosition  
 Rufen Sie diese Methode, um die aktuelle Zeigerposition für die Datei zu erhalten.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Die Position in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) zum Abrufen der aktuellen Position des Datei-Zeiger.  
  
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
 Aufrufe [' GetFileSize '](http://msdn.microsoft.com/library/windows/desktop/aa364955) zum Abrufen der Größe der Datei in Bytes.  
  
##  <a name="lockrange"></a>CAtlFile::LockRange  
 Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse zugegriffen wird zu sperren.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Die Position in der Datei, in dem die Sperre beginnen soll.  
  
 `nCount`  
 Die Länge des Bytebereichs gesperrt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [Sperrdatei](http://msdn.microsoft.com/library/windows/desktop/aa365202) , einen Bereich in der Datei zu sperren. Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als ein Bereich einer Datei sperren, aber keine überlappenden Bereiche sind zulässig. Wenn Sie eine Region entsperrt werden, mithilfe von [CAtlFile::UnlockRange](#unlockrange), der Bytebereich muss genau in der Region, die zuvor gesperrt war entsprechen. `LockRange`angrenzende Regionen werden nicht zusammengeführt werden; Wenn zwei gesperrte Bereiche nebeneinander angeordnet sind, müssen Sie jede separat entsperren.  
  
##  <a name="m_ptm"></a>CAtlFile::m_pTM  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="read"></a>CAtlFile::Read  
 Rufen Sie diese Methode zum Lesen von Daten aus einer Datei, ab der Position des Dateizeigers erkennbar.  
  
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
 Zeiger auf den Puffer, der aus der Datei gelesenen Daten erhalten.  
  
 `nBufSize`  
 Die Puffergröße in Byte.  
  
 `nBytesRead`  
 Die Anzahl von gelesenen Bytes.  
  
 `pOverlapped`  
 Die überlappende Struktur. Finden Sie unter `lpOverlapped` in [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467) im Windows SDK.  
  
 `pfnCompletionRoutine`  
 Abschlussroutine beendet hat. Finden Sie unter *LpCompletionRoutine* in [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die ersten drei Formulare [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467), den letzten [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) zum Lesen von Daten aus der Datei. Verwendung [CAtlFile::Seek](#seek) den Dateizeiger verschoben.  
  
##  <a name="seek"></a>CAtlFile::Seek  
 Rufen Sie diese Methode, um den Dateizeiger der Datei zu verschieben.  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nOffset`  
 Der Offset vom den Anfangspunkt, die vom `dwFrom`.  
  
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
 Aufrufe [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) und [SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531) zum Festlegen der Größe der Datei. Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.  
  
##  <a name="unlockrange"></a>CAtlFile::UnlockRange  
 Rufen Sie diese Methode, um einen Bereich der Datei zu entsperren.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Die Position in der Datei, in dem das Entsperren beginnen soll.  
  
 `nCount`  
 Die Länge des Bytebereichs entsperrt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715) um einen Bereich der Datei zu entsperren.  
  
##  <a name="write"></a>CAtlFile::Write  
 Rufen Sie diese Methode zum Schreiben von Daten in der Datei, ab der Position des Dateizeigers erkennbar.  
  
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
 Der Puffer mit den Daten in die Datei geschrieben werden sollen.  
  
 `nBufSize`  
 Die Anzahl der Bytes, die aus dem Puffer übertragen werden.  
  
 `pOverlapped`  
 Die überlappende Struktur. Finden Sie unter `lpOverlapped` in [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747) im Windows SDK.  
  
 `pfnCompletionRoutine`  
 Abschlussroutine beendet hat. Finden Sie unter *LpCompletionRoutine* in [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) im Windows SDK.  
  
 `pnBytesWritten`  
 Die Bytes geschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die ersten drei Formulare [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747), ruft die letzte [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) Daten in die Datei schreiben. Verwendung [CAtlFile::Seek](#seek) den Dateizeiger verschoben.  
  
## <a name="see-also"></a>Siehe auch  
 [Laufschriften-Beispiel](../../visual-cpp-samples.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CHandle-Klasse](../../atl/reference/chandle-class.md)
