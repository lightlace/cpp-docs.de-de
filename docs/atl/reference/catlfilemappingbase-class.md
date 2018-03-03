---
title: CAtlFileMappingBase Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5e0dd90894e052d4b9bcff08e7e12234dde8f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase-Klasse
Diese Klasse stellt eine Speicherabbilddatei dar.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Der Konstruktor.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Rufen Sie diese Methode zum Kopieren aus einem Dateizuordnungsobjekt.|  
|[CAtlFileMappingBase::GetData](#getdata)|Rufen Sie diese Methode, um die Daten aus einer Dateizuordnungsobjekt abzurufen.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Rufen Sie diese Methode, um das Dateihandle zurückgeben.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Rufen Sie diese Methode, um die Zuordnung von einem Dateizuordnungsobjekt abzurufen.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Rufen Sie diese Methode zum Erstellen eines dateizuordnung Objekts.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Rufen Sie diese Methode, um eine Dateizuordnungsobjekt erstellen, die Vollzugriff auf alle Vorgänge ermöglicht.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Rufen Sie diese Methode, um ein Handle für das Dateizuordnungsobjekt zurückzugeben.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Rufen Sie diese Methode, um eine Dateizuordnungsobjekt aufheben.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Legt die aktuelle Dateizuordnungsobjekt auf einen anderen Dateizuordnungsobjekt fest.|  
  
## <a name="remarks"></a>Hinweise  
 Dateizuordnung ist die Zuordnung des Inhalts einer Datei zu einem Teil des virtuellen Adressraums eines Prozesses. Diese Klasse stellt Methoden zum Erstellen von dateizuordnung Objekten, mit denen Programme auf einfache Weise zugreifen und Freigeben von Daten bereit.  
  
 Weitere Informationen finden Sie unter [Datei zuordnen](http://msdn.microsoft.com/library/windows/desktop/aa366556) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase  
 Der Konstruktor.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `orig`  
 Die ursprüngliche Dateizuordnungsobjekt zu kopieren, um das neue Objekt zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt eine neue Dateizuordnungsobjekt, optional mit einem vorhandenen Objekt. Es ist dennoch erforderlich, rufen Sie [CAtlFileMappingBase::MapFile](#mapfile) öffnen oder erstellen das Dateizuordnungsobjekt für eine bestimmte Datei.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 Der Destruktor.  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle von der Klasse und die Aufrufe reservierten Ressourcen frei der [CAtlFileMappingBase::Unmap](#unmap) Methode.  
  
##  <a name="copyfrom"></a>CAtlFileMappingBase::CopyFrom  
 Rufen Sie diese Methode zum Kopieren aus einem Dateizuordnungsobjekt.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `orig`  
 Die ursprüngliche Dateizuordnungsobjekt zum Kopieren aus.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
##  <a name="getdata"></a>CAtlFileMappingBase::GetData  
 Rufen Sie diese Methode, um die Daten aus einer Dateizuordnungsobjekt abzurufen.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die Daten an.  
  
##  <a name="gethandle"></a>CAtlFileMappingBase::GetHandle  
 Rufen Sie diese Methode, um ein Handle für das Dateizuordnungsobjekt zurückzugeben.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle für das Dateizuordnungsobjekt zurück.  
  
##  <a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize  
 Rufen Sie diese Methode, um die Zuordnung von einem Dateizuordnungsobjekt abzurufen.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe der Zuordnung zurück.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapfile"></a>CAtlFileMappingBase::MapFile  
 Rufen Sie diese Methode zum Öffnen oder erstellen Sie eine Dateizuordnungsobjekt für die angegebene Datei.  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hFile`  
 Handle für die Datei aus dem ein Zuordnungsobjekt zu erstellen. `hFile`muss gültig sein und kann nicht auf INVALID_HANDLE_VALUE festgelegt werden.  
  
 `nMappingSize`  
 Die Größe der Zuordnung. Bei 0 ist die maximale Größe der dateizuordnung Objekts gleich der aktuellen Größe der identifizierten Datei *hFile.*  
  
 `nOffset`  
 Die Dateioffset, in denen Zuordnung begonnen werden soll. Der Offset-Wert muss ein Vielfaches des Systems Arbeitsspeicher Zuordnung Granularität sein.  
  
 `dwMappingProtection`  
 Der Schutz für die Dateiansicht gewünscht wird, wenn die Datei zugeordnet ist. Finden Sie unter `flProtect` in [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) im Windows SDK.  
  
 `dwViewDesiredAccess`  
 Gibt den Typ des Zugriffs auf die Datei anzeigen und somit den Schutz der Seiten, die von der Datei zugeordnet. Finden Sie unter `dwDesiredAccess` in [Fehler bei MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem eine Dateizuordnungsobjekt erstellt wurde, darf die Größe der Datei nicht die Größe der dateizuordnung Objekts; Wenn dies der Fall ist, werden nicht alle der Inhalt der Datei zur Freigabe sein. Weitere Informationen finden Sie unter [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) und [Fehler bei MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem  
 Rufen Sie diese Methode, um eine Dateizuordnungsobjekt erstellen, die Vollzugriff auf alle Vorgänge ermöglicht.  
  
```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nMappingSize`  
 Die Größe der Zuordnung. Bei 0 ist die maximale Größe der dateizuordnung Objekts gleich der aktuellen Größe des Dateizuordnungsobjekt, identifiziert durch`szName.`  
  
 `szName`  
 Der Name des Objekts Zuordnung.  
  
 *pbAlreadyExisted*  
 Verweist auf ein BOOL-Wert, der auf "true" das Zuordnungsobjekt bereits festgelegt ist vorhanden waren.  
  
 `lpsa`  
 Der Zeiger auf eine **SECURITY_ATTRIBUTES** -Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Finden Sie unter *LpAttributes* in [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) im Windows SDK.  
  
 `dwMappingProtection`  
 Der Schutz für die Dateiansicht gewünscht wird, wenn die Datei zugeordnet ist. Finden Sie unter `flProtect` in **CreateFileMapping** im Windows SDK.  
  
 `dwViewDesiredAccess`  
 Gibt den Typ des Zugriffs auf die Datei anzeigen und somit den Schutz der Seiten, die von der Datei zugeordnet. Finden Sie unter `dwDesiredAccess` in [Fehler bei MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 **MapShareMem** können Sie ein vorhandenes dateizuordnung Objekt erstellt, indem [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), um zwischen Prozessen gemeinsam genutzt werden.  
  
##  <a name="openmapping"></a>CAtlFileMappingBase::OpenMapping  
 Rufen Sie diese Methode, um eine benannte Dateizuordnungsobjekt für die angegebene Datei zu öffnen.  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `szName`  
 Der Name des Objekts Zuordnung. Wenn ein offenes Handle zu einem Dateizuordnungsobjekt mit diesem Namen vorhanden ist und die Sicherheitsbeschreibung für das Zuordnungsobjekt nicht zu Konflikten mit den `dwViewDesiredAccess` -Parameter, der Öffnungsvorgang erfolgreich war.  
  
 `nMappingSize`  
 Die Größe der Zuordnung. Bei 0 ist die maximale Größe der dateizuordnung Objekts gleich der aktuellen Größe des Dateizuordnungsobjekt, identifiziert durch`szName.`  
  
 `nOffset`  
 Die Dateioffset, in denen Zuordnung begonnen werden soll. Der Offset-Wert muss ein Vielfaches des Systems Arbeitsspeicher Zuordnung Granularität sein.  
  
 `dwViewDesiredAccess`  
 Gibt den Typ des Zugriffs auf die Datei anzeigen und somit den Schutz der Seiten, die von der Datei zugeordnet. Finden Sie unter `dwDesiredAccess` in [Fehler bei MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds tritt ein Assertionsfehler, wenn die Eingabeparameter ungültig sind.  
  
##  <a name="operator_eq"></a>CAtlFileMappingBase::operator =  
 Legt die aktuelle Dateizuordnungsobjekt auf einen anderen Dateizuordnungsobjekt fest.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Parameter  
 `orig`  
 Die aktuelle Dateizuordnungsobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das aktuelle Objekt zurück.  
  
##  <a name="unmap"></a>CAtlFileMappingBase::Unmap  
 Rufen Sie diese Methode, um eine Dateizuordnungsobjekt aufheben.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) in das Windows SDK für weitere Details.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlFileMapping-Klasse](../../atl/reference/catlfilemapping-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
