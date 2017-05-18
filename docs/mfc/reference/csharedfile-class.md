---
title: Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- memory files
- CSharedFile class
- shared memory files
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f812b2c7b8e3b158068bf3fdab0a327460056251
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csharedfile-class"></a>Klasse
Die [CMemFile](../../mfc/reference/cmemfile-class.md)-abgeleitete Klasse, die unterstützt freigegebene Dateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Erstellt ein `CSharedFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Schließt die shared Memory-Datei, und das Handle für den Speicherblock zurück.|  
|[CSharedFile::SetHandle](#sethandle)|Fügt die shared Memory-Datei in einen Speicherblock.|  
  
## <a name="remarks"></a>Hinweise  
 Speicherdateien Verhalten sich wie Dateien, mit der Ausnahme, dass die Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert ist. Eine Datei ist hilfreich beim schnellen temporären Speicher und zum Übertragen von unformatierten Bytes oder serialisierten Objekten zwischen voneinander unabhängige Prozesse.  
  
 Shared Memory-Dateien unterscheiden sich von anderen Dateien, da Speicher für diese mit belegt wird die [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows-Funktion. Die `CSharedFile` Klasse speichert Daten in einem global belegten Speicherblocks (erstellt mit **GlobalAlloc**), und diesem Speicherblock freigegeben werden kann mithilfe von DDE, der Zwischenablage oder andere OLE/COM uniform Data Transfer Vorgänge, z. B. mit `IDataObject`.  
  
 **GlobalAlloc** gibt eine `HGLOBAL` behandeln, anstatt ein Zeiger auf Speicher, z. B. der zurückgegebene Zeiger [Malloc](../../c-runtime-library/reference/malloc.md). Die `HGLOBAL` Handle wird in bestimmten Applikationen benötigt. Zum Beispiel von Daten in die Zwischenablage müssen Sie eine `HGLOBAL` behandeln.  
  
 Beachten Sie, dass `CSharedFile` keine Verwendung speicherzugeordnete Dateien und Daten können nicht direkt zwischen Prozessen freigegeben werden.  
  
 `CSharedFile`Objekte können ihre eigenen Speicher automatisch oder anfügen, die Ihre eigenen Speicherblock, der die `CSharedFile` -Objekt durch Aufrufen von [CSharedFile::SetHandle](#sethandle). In beiden Fällen wird im Speicher für die Speicherdatei automatisch vergrößern reserviert `nGrowBytes`-Größe erhöht, wenn `nGrowBytes` ist nicht&0; (null).  
  
 Weitere Informationen finden Sie im Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="csharedfile"></a>CSharedFile::CSharedFile  
 Erstellt ein `CSharedFile` -Objekt und belegt Speicherplatz.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>Parameter  
 *nAllocFlags*  
 Flags, der angibt, wie Arbeitsspeicher zugeordnet werden. Finden Sie unter [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) eine Liste der gültigen Werte.  
  
 `nGrowBytes`  
 Die Schrittweite Zuordnung für Arbeitsspeicher in Bytes.  
  
##  <a name="detach"></a>CSharedFile::Detach  
 Rufen Sie diese Funktion zum Schließen der Speicherdatei und der Speicherblock trennen.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Speicherblock, der den Inhalt der Datei für den Speicher enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können es erneut öffnen, wenn Sie aufrufen [SetHandle](#sethandle), verwenden das zurückgegebene Handle **trennen**.  
  
##  <a name="sethandle"></a>CSharedFile::SetHandle  
 Mit dieser Funktion können Sie einen Block von globalen Arbeitsspeicher zum Anfügen der `CSharedFile` Objekt.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *hGlobalMemory*  
 Handle für den globalen Speicher an die `CSharedFile`.  
  
 `bAllowGrow`  
 Gibt an, ob der Speicherblock zugelassen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bAllowGrow` ist ungleich NULL ist, die Größe des Speicherblocks wird erhöht als erforderlich, z. B. wenn versucht wird versucht, mehr Bytes zum Schreiben der Datei als für den Speicherblock zugewiesen wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)

