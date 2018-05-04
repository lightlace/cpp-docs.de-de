---
title: IAtlStringMgr Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05d7ff0a38c0a557016887e6fce92fcb0bf28226
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr-Klasse
Diese Klasse stellt die Schnittstelle, um eine `CStringT` Speicher-Manager.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Zuordnen](#allocate)|Rufen Sie diese Methode, um eine neue Zeichenfolge Datenstruktur zu reservieren.|  
|[Klon](#clone)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf einen neuen Zeichenfolge-Manager für die Verwendung mit einer anderen Instanz von `CSimpleStringT`.|  
|[Frei](#free)|Rufen Sie diese Methode, um eine Datenstruktur Zeichenfolge frei.|  
|[GetNilString](#getnilstring)|Gibt einen Zeiger auf die `CStringData` durch leere Zeichenfolgenobjekten verwendete Objekt.|  
|[Wenn ein Speicher neu](#reallocate)|Rufen Sie diese Methode, um eine Datenstruktur Zeichenfolge neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle verwaltet den Arbeitsspeicher, die von den Klassen der MFC-unabhängigen Zeichenfolge verwendet. z. B. [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), und [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Diese Klasse können auch um einen benutzerdefinierten Speicher-Manager für die benutzerdefinierte Zeichenfolge-Klasse zu implementieren. Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  
  
##  <a name="allocate"></a>  IAtlStringMgr::Allocate  
 Ordnet eine neue Zeichenfolge-Datenstruktur an.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nAllocLength`  
 Die Anzahl der Zeichen im neuen Speicherblock.  
  
 `nCharSize`  
 Die Größe (in Bytes) der den Zeichentyp, der von der String-Manager verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den neu belegten Speicherblock zurück.  
  
> [!NOTE]
>  Signalisieren Sie eine fehlerhafte Zuordnung nicht durch eine Ausnahme auszulösen. Stattdessen sollte eine fehlerhafte Zuordnung signalisiert werden, wird durch zurückgeben **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [IAtlStringMgr::Free](#free) oder [IAtlStringMgr::ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="clone"></a>  IAtlStringMgr::Clone  
 Gibt einen Zeiger auf einen neuen Zeichenfolge-Manager für die Verwendung mit einer anderen Instanz von `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie der `IAtlStringMgr` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Im Allgemeinen vom Framework aufgerufen, wenn ein Zeichenfolgen-Manager für eine neue Zeichenfolge benötigt wird. In den meisten Fällen die **dies** Zeiger zurückgegeben.  
  
 Jedoch, wenn der Speicher-Manager nicht unterstützt, die von mehreren Instanzen von verwendet wird `CSimpleStringT`, ein Zeiger auf einen Manager teilbar Zeichenfolge zurückgegeben werden soll.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="free"></a>  IAtlStringMgr::Free  
 Gibt eine Zeichenfolge Datenstruktur frei.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Ein Zeiger auf den Speicherblock freigegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den angegebenen Speicherblock, der zuvor von belegten [Allocate](#allocate) oder [weisen](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString  
 Gibt einen Zeiger auf eine Zeichenfolge Datenstruktur für eine leere Zeichenfolge zurück.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CStringData` Objekt verwendet, um eine leere Zeichenfolge darzustellen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um eine Darstellung eine leere Zeichenfolge zurück.  
  
> [!NOTE]
>  Wenn Sie einen benutzerdefinierte Zeichenfolge-Manager implementieren möchten, muss diese Funktion nie fehl. Sie können dies sicherstellen, durch das Einbetten von einer Instanz von **CNilStringData** Zeichenfolgenklasse-Manager, und Rückgabe einen Zeiger auf diese Instanz.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="reallocate"></a>  IAtlStringMgr::Reallocate  
 Ordnet eine Zeichenfolge-Datenstruktur an.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Ein Zeiger auf die zuvor von diesem Speicher-Manager belegten Arbeitsspeichers.  
  
 `nAllocLength`  
 Die Anzahl der Zeichen im neuen Speicherblock.  
  
 `nCharSize`  
 Die Größe (in Bytes) der den Zeichentyp, der von der String-Manager verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Ändern der Größe des vorhandenen Speicherblocks gemäß `pData`.  
  
 Rufen Sie [IAtlStringMgr::Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


