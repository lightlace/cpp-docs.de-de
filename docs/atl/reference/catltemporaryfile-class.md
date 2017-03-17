---
title: Klasse CAtlTemporaryFile | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
dev_langs:
- C++
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
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
ms.openlocfilehash: 9673c5a137feddb0eb696945ec6abeb5f3cb062e
ms.lasthandoff: 02/24/2017

---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile-Klasse
Diese Klasse stellt Methoden für die Erstellung und Verwendung einer temporären Datei.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlTemporaryFile
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Der Konstruktor.|  
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](#close)|Rufen Sie diese Methode, um eine temporäre Datei zu schließen und seinen Inhalt löschen oder speichern Sie sie unter dem angegebenen Dateinamen.|  
|[CAtlTemporaryFile::Create](#create)|Rufen Sie diese Methode zum Erstellen einer temporären Datei.|  
|[CAtlTemporaryFile::Flush](#flush)|Rufen Sie diese Methode, um zu erzwingen, dass alle Daten in der Dateipuffer in die temporäre Datei geschrieben werden.|  
|[CAtlTemporaryFile::GetPosition](#getposition)|Rufen Sie diese Methode, um die aktuelle Dateiposition Zeiger zu erhalten.|  
|[CAtlTemporaryFile::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der Größe in Byte der temporären Datei.|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|Rufen Sie diese Methode, um die Zuordnung aufheben, die Datei aus der `CAtlTemporaryFile` Objekt.|  
|[CAtlTemporaryFile::HandsOn](#handson)|Rufen Sie diese Methode, um eine vorhandene temporäre Datei zu öffnen und den Zeiger am Ende der Datei.|  
|[CAtlTemporaryFile::LockRange](#lockrange)|Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse Zugriff zu sperren.|  
|[CAtlTemporaryFile::Read](#read)|Rufen Sie diese Methode zum Lesen von Daten aus der temporären Datei, die an der Position des Zeigers Datei ab.|  
|[CAtlTemporaryFile::Seek](#seek)|Rufen Sie diese Methode, um den Zeiger der temporären Datei zu verschieben.|  
|[CAtlTemporaryFile::SetSize](#setsize)|Rufen Sie diese Methode, um die Größe der temporären Datei festlegen.|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Rufen Sie diese Methode, um den Namen der temporären Datei zurückzugeben.|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Rufen Sie diese Methode, um einen Bereich der temporären Datei zu entsperren.|  
|[CAtlTemporaryFile::Write](#write)|Rufen Sie diese Methode, um Daten in die temporäre Datei, ab der Position des Zeigers Datei zu schreiben.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator HANDLE](#operator_handle)|Gibt ein Handle an die temporäre Datei.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlTemporaryFile`erleichtert Ihnen zum Erstellen und Verwenden einer temporären Datei. Die Datei wird automatisch mit dem Namen, geöffnet, geschlossen und gelöscht. Wenn Sie den Inhalt der Datei erforderlich sind, nachdem die Datei geschlossen wird, können sie in eine neue Datei mit dem angegebenen Namen gespeichert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile  
 Der Konstruktor.  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei wird nicht tatsächlich geöffnet, bis ein Aufruf [CAtlTemporaryFile::Create](#create).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#73;](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 Der Destruktor.  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor ruft [CAtlTemporaryFile::Close](#close).  
  
##  <a name="close"></a>CAtlTemporaryFile::Close  
 Rufen Sie diese Methode, um eine temporäre Datei zu schließen und seinen Inhalt löschen oder speichern Sie sie unter dem angegebenen Dateinamen.  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *szNewName*  
 Der Name für die neue Datei in den Inhalt der temporären Datei zu speichern. Wenn dieses Argument NULL ist, werden die Inhalte der temporären Datei gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="create"></a>CAtlTemporaryFile::Create  
 Rufen Sie diese Methode zum Erstellen einer temporären Datei.  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszDir`  
 Der Pfad für die temporäre Datei. Wenn NULL ist, wird dies [GetTempPath](http://msdn.microsoft.com/library/windows/desktop/aa364992) aufgerufen, um einen Pfad zuweisen.  
  
 `dwDesiredAccess`  
 Der gewünschte Zugriff. Finden Sie unter `dwDesiredAccess` in [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="flush"></a>CAtlTemporaryFile::Flush  
 Rufen Sie diese Methode, um zu erzwingen, dass alle Daten in der Dateipuffer in die temporäre Datei geschrieben werden.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie [CAtlTemporaryFile::HandsOff](#handsoff), außer dass die Datei nicht geschlossen wird.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="getposition"></a>CAtlTemporaryFile::GetPosition  
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
 Verwenden Sie zum Ändern der Position des Dateizeigers [CAtlTemporaryFile::Seek](#seek).  
  
##  <a name="getsize"></a>CAtlTemporaryFile::GetSize  
 Rufen Sie diese Methode zum Abrufen der Größe in Byte der temporären Datei.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nLen`  
 Die Anzahl der Bytes in der Datei.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
##  <a name="handsoff"></a>CAtlTemporaryFile::HandsOff  
 Rufen Sie diese Methode, um die Zuordnung aufheben, die Datei aus der `CAtlTemporaryFile` Objekt.  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 `HandsOff`und [CAtlTemporaryFile::HandsOn](#handson) werden verwendet, um die Datei aus dem Objekt aufgehoben, und bei Bedarf erneut an. `HandsOff`wird erzwingen, dass alle Daten verbleiben in der Dateipuffer in die temporäre Datei geschrieben werden sollen, und schließen Sie die Datei. Wenn Sie schließen und die Datei dauerhaft löschen möchten, oder gegebenenfalls zu schließen und den Inhalt der Datei mit dem angegebenen Namen, [CAtlTemporaryFile::Close](#close).  
  
##  <a name="handson"></a>CAtlTemporaryFile::HandsOn  
 Rufen Sie diese Methode, um eine vorhandene temporäre Datei zu öffnen und den Zeiger am Ende der Datei.  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 [CAtlTemporaryFile::HandsOff](#handsoff) und `HandsOn` werden verwendet, um die Datei aus dem Objekt aufgehoben, und bei Bedarf erneut an.  
  
##  <a name="lockrange"></a>CAtlTemporaryFile::LockRange  
 Rufen Sie diese Methode, um einen Bereich in der temporären Datei, um zu verhindern, dass andere Prozesse zugreifen darauf zu sperren.  
  
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
 Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehrere Bereiche einer Datei sperren, jedoch keine überlappenden Bereiche sind zulässig. Verwenden, um einen Bereich erfolgreich zu entsperren, [CAtlTemporaryFile::UnlockRange](#unlockrange), sicherstellen der Bytebereich entspricht genau der Region, die zuvor gesperrt war. `LockRange`nicht zusammen benachbarte Bereiche; Wenn zwei gesperrte Bereiche nebeneinander angeordnet sind, müssen Sie jeweils einzeln entsperren.  
  
##  <a name="operator_handle"></a>CAtlTemporaryFile::operator HANDLE  
 Gibt ein Handle an die temporäre Datei.  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="read"></a>CAtlTemporaryFile::Read  
 Rufen Sie diese Methode zum Lesen von Daten aus der temporären Datei, die an der Position des Zeigers Datei ab.  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pBuffer`  
 Zeiger auf den Puffer, der die Daten empfängt, die aus der Datei gelesen werden.  
  
 `nBufSize`  
 Die Puffergröße in Byte.  
  
 `nBytesRead`  
 Die Anzahl von gelesenen Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Rufen Sie zum Ändern der Position des Dateizeigers [CAtlTemporaryFile::Seek](#seek).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="seek"></a>CAtlTemporaryFile::Seek  
 Rufen Sie diese Methode, um den Zeiger der temporären Datei zu verschieben.  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nOffset`  
 Der Offset in Bytes vom Ausgangspunkt vom *DwFrom.*  
  
 `dwFrom`  
 Der Anfangspunkt (FILE_BEGIN, FILE_CURRENT oder FILE_END).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Rufen Sie zum Abrufen der aktuellen Datei Mauszeigerposition [CAtlTemporaryFile::GetPosition](#getposition).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="setsize"></a>CAtlTemporaryFile::SetSize  
 Rufen Sie diese Methode, um die Größe der temporären Datei festlegen.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nNewLen`  
 Die neue Länge der Datei in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.  
  
##  <a name="tempfilename"></a>CAtlTemporaryFile::TempFileName  
 Rufen Sie diese Methode, um die temporäre Datei zurück.  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `LPCTSTR` auf den Dateinamen zeigen.  
  
### <a name="remarks"></a>Hinweise  
 Der Dateiname wird in generiert [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) mit einem Aufruf der [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991) [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Funktion. Die Erweiterung wird immer "TFR" für die temporäre Datei sein.  
  
##  <a name="unlockrange"></a>CAtlTemporaryFile::UnlockRange  
 Rufen Sie diese Methode, um einen Bereich der temporären Datei zu entsperren.  
  
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
 Aufrufe [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).  
  
##  <a name="write"></a>CAtlTemporaryFile::Write  
 Rufen Sie diese Methode, um Daten in die temporäre Datei, ab der Position des Zeigers Datei zu schreiben.  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pBuffer`  
 Der Puffer mit den Daten in die Datei geschrieben werden.  
  
 `nBufSize`  
 Die Anzahl der Bytes, die aus dem Puffer übertragen werden.  
  
 `pnBytesWritten`  
 Die Anzahl der geschriebenen Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CAtlFile-Klasse](../../atl/reference/catlfile-class.md)

