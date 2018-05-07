---
title: Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs:
- C++
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bee22940fb197d480f4ae3550d8dd59780c256b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="csharedfile-class"></a>Klasse
Die [CMemFile](../../mfc/reference/cmemfile-class.md)-abgeleitete Klasse, die unterstützt die freigegebene arbeitsspeicherdateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Erstellt ein `CSharedFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Schließt das shared Memory-Datei und gibt das Handle der Speicherblock zurück.|  
|[CSharedFile::SetHandle](#sethandle)|Fügt das shared Memory-Datei in einen Speicherblock.|  
  
## <a name="remarks"></a>Hinweise  
 Arbeitsspeicherdateien Verhalten wie Dateien auf Datenträgern, außer dass die Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert wird. Eine Arbeitsspeicherdatei eignet sich für die schnelle temporäre Speicherung oder zum Übertragen von unformatierten Bytes oder serialisiert Objekte zwischen unabhängigen Prozessen.  
  
 Freigegebene arbeitsspeicherdateien unterscheiden sich von anderen Speicherdateien, insofern, dass Arbeitsspeicher dafür zugeordnet wird, mit der [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows-Funktion. Die `CSharedFile` Klasse speichert Daten in eine Global belegten Speicherblocks (erstellt mit **GlobalAlloc**), und diesem Speicherblock mit DDE, die Zwischenablage oder andere OLE/COM uniform Data Transfer Vorgänge, z. B. freigegeben werden kann Mithilfe von `IDataObject`.  
  
 **GlobalAlloc** gibt eine `HGLOBAL` behandeln, anstatt ein Zeiger auf Speicher, z. B. der zurückgegebene Zeiger ["malloc"](../../c-runtime-library/reference/malloc.md). Die `HGLOBAL` Handle in bestimmten Anwendungen benötigt wird. Beispielsweise, um Daten zu speichern, auf die Zwischenablage müssen Sie eine `HGLOBAL` behandeln.  
  
 Bitte beachten Sie, dass `CSharedFile` keine Verwendung speicherzugeordnete Dateien und die Daten können nicht direkt zwischen Prozessen freigegeben werden.  
  
 `CSharedFile` Objekte können automatisch ihre eigenen Speicher zuordnen, oder Sie können eigene Speicherblocks zum Anfügen der `CSharedFile` Objekt durch Aufrufen von [CSharedFile::SetHandle](#sethandle). In beiden Fällen wird im Arbeitsspeicher für die Speicherdatei automatisch vergrößern reserviert `nGrowBytes`-Größe erhöht, wenn `nGrowBytes` ist nicht 0 (null).  
  
 Weitere Informationen finden Sie im Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="csharedfile"></a>  CSharedFile::CSharedFile  
 Erstellt ein `CSharedFile` -Objekt und teilt Arbeitsspeicher für sie.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>Parameter  
 *nAllocFlags*  
 Flags, der angibt, wie Arbeitsspeicher zugeordnet werden. Finden Sie unter [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) eine Liste der gültigen Flagwerte.  
  
 `nGrowBytes`  
 Das Inkrement Zuweisung, Arbeitsspeicher in Bytes.  
  
##  <a name="detach"></a>  CSharedFile::Detach  
 Rufen Sie diese Funktion, um die Arbeitsspeicher-Datendatei zu schließen und trennen Sie sie aus der Speicherblock.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Speicherblock, der den Inhalt der Arbeitsspeicherdatei enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können es erneut öffnen, wenn Sie aufrufen [SetHandle](#sethandle), verwenden das zurückgegebene Handle **trennen**.  
  
##  <a name="sethandle"></a>  CSharedFile::SetHandle  
 Mit dieser Funktion können Sie einen Block von globalen Arbeitsspeicher zum Anfügen der `CSharedFile` Objekt.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *hGlobalMemory*  
 Handle für den globalen Speicher zugeordnet werden soll die `CSharedFile`.  
  
 `bAllowGrow`  
 Gibt an, ob der Speicherblock zulässig ist, vergrößert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bAllowGrow` ist ungleich NULL ist, die Größe des Speicherblocks ist erhöht, nach Bedarf, z. B. wenn ein Versuch ist versucht, mehr Bytes zu schreiben, in die Datei als für den Speicherblock zugewiesen wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)
