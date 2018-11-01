---
title: CAtlFileMappingBase-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: 71b3b8621f4148f680337e9bce6ef469b90de746
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614378"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase-Klasse

Diese Klasse stellt eine Datei mit zugewiesenem Speicher.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Rufen Sie diese Methode zum Kopieren aus einem Dateizuordnungsobjekt auf.|
|[CAtlFileMappingBase::GetData](#getdata)|Rufen Sie diese Methode, um die Daten aus einer Dateizuordnungsobjekt abzurufen.|
|[CAtlFileMappingBase::GetHandle](#gethandle)|Rufen Sie diese Methode, um das Dateihandle zurückgeben.|
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Rufen Sie diese Methode, um die Zuordnung von einem dateizuordnung Objekt abzurufen.|
|[CAtlFileMappingBase::MapFile](#mapfile)|Rufen Sie diese Methode zum Erstellen eines Datei-Zuordnungs-Objekts.|
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Rufen Sie diese Methode zum Erstellen eines Datei-Zuordnungs-Objekts, das Vollzugriff auf alle Prozesse ermöglicht.|
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Rufen Sie diese Methode, um ein Handle für das Dateizuordnungsobjekt zurückzugeben.|
|[CAtlFileMappingBase::Unmap](#unmap)|Rufen Sie diese Methode, um eine Dateizuordnungsobjekt aufheben.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlFileMappingBase::operator =](#operator_eq)|Legt das aktuelle dateizuordnung Objekt in ein anderes dateizuordnung Objekt fest.|

## <a name="remarks"></a>Hinweise

-Dateizuordnung die Datei ist die Zuordnung des Inhalts einer Datei zu einem Teil des virtuellen Adressraums eines Prozesses. Diese Klasse stellt Methoden zum Erstellen von dateizuordnung Objekten, mit denen Programme auf einfache Weise zugreifen und Freigeben von Daten bereit.

Weitere Informationen finden Sie unter [Dateizuordnung](/windows/desktop/Memory/file-mapping) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlfile.h

##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase

Der Konstruktor.

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>Parameter

*orig*<br/>
Das ursprüngliche dateizuordnung Objekt zum Erstellen des neuen Objekts kopiert.

### <a name="remarks"></a>Hinweise

Erstellt eine neue Dateizuordnungsobjekt, optional mithilfe eines vorhandenen Objekts. Es ist immer noch notwendig, [CAtlFileMappingBase::MapFile](#mapfile) öffnen oder erstellen das Dateizuordnungsobjekt für eine bestimmte Datei.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase

Der Destruktor.

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle von der Klasse und ruft zugeordneten Ressourcen frei der [CAtlFileMappingBase::Unmap](#unmap) Methode.

##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom

Rufen Sie diese Methode zum Kopieren aus einem Dateizuordnungsobjekt auf.

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>Parameter

*orig*<br/>
Die ursprüngliche Dateizuordnungsobjekt zum Kopieren aus.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="getdata"></a>  CAtlFileMappingBase::GetData

Rufen Sie diese Methode, um die Daten aus einer Dateizuordnungsobjekt abzurufen.

```
void* GetData() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die Daten an.

##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle

Rufen Sie diese Methode, um ein Handle für das Dateizuordnungsobjekt zurückzugeben.

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für das Dateizuordnungsobjekt zurück.

##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize

Rufen Sie diese Methode, um die Zuordnung von einem dateizuordnung Objekt abzurufen.

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Größe der Zuordnung zurück.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).

##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile

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

*hFile*<br/>
Handle für die Datei aus dem ein Zuordnungsobjekt zu erstellen. *hFile* muss gültig sein und kann nicht festgelegt werden, um INVALID_HANDLE_VALUE.

*nMappingSize*<br/>
Die Größe für Zuordnung. Wenn 0, ist die maximale Größe der dateizuordnung Objekts gleich der aktuellen Größe der Datei identifizierte *hFile.*

*nOffset*<br/>
Die Dateioffset, in dem Zuordnung ist, um zu beginnen. Der Offset-Wert muss es sich um ein Vielfaches von Speicher-zuordnungsgranularität des Systems sein.

*dwMappingProtection*<br/>
Der Schutz für die Dateiansicht gewünscht wird, wenn die Datei zugeordnet ist. Finden Sie unter *FlProtect* in [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) im Windows SDK.

*dwViewDesiredAccess*<br/>
Gibt den Typ des Zugriffs auf die Datei anzeigen und somit den Schutz von der Seiten, die von der Datei zugeordnet. Finden Sie unter *DwDesiredAccess* in [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Nachdem eine Dateizuordnungsobjekt erstellt wurde, darf die Größe der dateizuordnung Objekts von der Größe der Datei nicht überschreiten. Wenn dies der Fall ist, werden nicht alle der Inhalt der Datei für die Freigabe zur Verfügung. Weitere Informationen finden Sie unter [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) und [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).

##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem

Rufen Sie diese Methode zum Erstellen eines Datei-Zuordnungs-Objekts, das Vollzugriff auf alle Prozesse ermöglicht.

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

*nMappingSize*<br/>
Die Größe für Zuordnung. Bei 0 wird die maximale Größe der dateizuordnung Objekts gleich der aktuellen Größe des der identifizierte Dateizuordnungsobjekt *SzName*.

*szName*<br/>
Der Name des Objekts Zuordnung.

*pbAlreadyExisted*<br/>
Verweist auf ein BOOL-Wert, der auf "true" fest, wenn das Zuordnungsobjekt bereits festgelegt ist vorhanden.

*lpsa*<br/>
Der Zeiger auf eine `SECURITY_ATTRIBUTES` -Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Finden Sie unter *LpAttributes* in [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) im Windows SDK.

*dwMappingProtection*<br/>
Der Schutz für die Dateiansicht, gewünscht wird, wenn die Datei zugeordnet ist. Finden Sie unter *FlProtect* in `CreateFileMapping` im Windows SDK.

*dwViewDesiredAccess*<br/>
Gibt den Typ des Zugriffs auf die Datei anzeigen und somit den Schutz von der Seiten, die von der Datei zugeordnet. Finden Sie unter *DwDesiredAccess* in [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`MapShareMem` können Sie ein vorhandenes dateizuordnung Objekt erstellt, indem [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga), um zwischen Prozessen gemeinsam genutzt werden.

##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping

Rufen Sie diese Methode, um eine benannte Dateizuordnungsobjekt für die angegebene Datei zu öffnen.

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Parameter

*szName*<br/>
Der Name des Objekts Zuordnung. Wenn ein offenes Handle zu einem Dateizuordnungsobjekt mit diesem Namen vorhanden ist und die Sicherheitsbeschreibung für das Zuordnungsobjekt nicht zu Konflikten mit der *DwViewDesiredAccess* Parameter, der geöffnete Vorgang erfolgreich ist.

*nMappingSize*<br/>
Die Größe für Zuordnung. Bei 0 wird die maximale Größe der dateizuordnung Objekts gleich der aktuellen Größe des der identifizierte Dateizuordnungsobjekt *SzName*.

*nOffset*<br/>
Die Dateioffset, in dem Zuordnung ist, um zu beginnen. Der Offset-Wert muss es sich um ein Vielfaches von Speicher-zuordnungsgranularität des Systems sein.

*dwViewDesiredAccess*<br/>
Gibt den Typ des Zugriffs auf die Datei anzeigen und somit den Schutz von der Seiten, die von der Datei zugeordnet. Finden Sie unter *DwDesiredAccess* in [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Assertionsfehler, wenn der Eingabeparameter ungültig sind.

##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =

Legt das aktuelle dateizuordnung Objekt in ein anderes dateizuordnung Objekt fest.

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>Parameter

*orig*<br/>
Das aktuelle dateizuordnung Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das aktuelle Objekt zurück.

##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap

Rufen Sie diese Methode, um eine Dateizuordnungsobjekt aufheben.

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [UnmapViewOfFile](https://msdn.microsoft.com/library/windows/desktop/aa366882) im Windows SDK für weitere Details.

## <a name="see-also"></a>Siehe auch

[CAtlFileMapping-Klasse](../../atl/reference/catlfilemapping-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
