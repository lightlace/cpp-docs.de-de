---
title: IAtlStringMgr Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlStringMgr
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4ff4aa01a6d30f377560962f98a5892bdcc37837
ms.lasthandoff: 02/24/2017

---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr-Klasse
Diese Klasse stellt die Schnittstelle zu einem `CStringT` Speicher-Manager.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Zuordnen](#allocate)|Rufen Sie diese Methode, um eine neue Zeichenfolge Datenstruktur reservieren.|  
|[Klonen](#clone)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf eine neue Zeichenfolge-Manager für die Verwendung mit einer anderen Instanz von `CSimpleStringT`.|  
|[Kostenlose](#free)|Rufen Sie diese Methode, um eine Datenstruktur Zeichenfolge freizugeben.|  
|[GetNilString](#getnilstring)|Gibt einen Zeiger auf das `CStringData` -Objekt von leeren String-Objekten verwendet.|  
|[Neu zuordnen](#reallocate)|Rufen Sie diese Methode, um eine String-Datenstruktur neu zuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle verwaltet den Speicher, die von den MFC-unabhängigen String-Klassen verwendet. z. B. [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), und [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Diese Klasse können auch einen benutzerdefinierten Speicher-Manager für die benutzerdefinierte Zeichenfolge-Klasse implementieren. Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  
  
##  <a name="a-nameallocatea--iatlstringmgrallocate"></a><a name="allocate"></a>IAtlStringMgr::Allocate  
 Ordnet eine neue Zeichenfolge Datenstruktur.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nAllocLength`  
 Die Anzahl der Zeichen in der neuen Speicherblock.  
  
 `nCharSize`  
 Die Größe (in Byte) der den Zeichentyp von Zeichenfolgen-Manager verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den neu belegten Speicherblock zurück.  
  
> [!NOTE]
>  Signalisieren Sie eine fehlerhafte Zuweisung nicht durch Auslösen einer Ausnahme. Stattdessen sollte eine fehlerhafte Zuweisung signalisiert werden, durch die Rückgabe **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [IAtlStringMgr::Free](#free) oder [IAtlStringMgr::ReAllocate](#reallocate) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-nameclonea--iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr::Clone  
 Gibt einen Zeiger auf eine neue Zeichenfolge-Manager für die Verwendung mit einer anderen Instanz von `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie der `IAtlStringMgr` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Im Allgemeinen vom Framework aufgerufen, wenn ein Zeichenfolgen-Manager für eine neue Zeichenfolge benötigt wird. In den meisten Fällen die **dies** Zeiger zurückgegeben.  
  
 Jedoch, wenn der Speicher-Manager nicht unterstützt, verwendet wird, indem Sie mehrere Instanzen von `CSimpleStringT`, ein Zeiger auf ein allgemein anwendbares Zeichenfolge-Manager zurückgegeben werden soll.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namefreea--iatlstringmgrfree"></a><a name="free"></a>IAtlStringMgr::Free  
 Gibt eine Zeichenfolge-Datenstruktur frei.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Ein Zeiger auf den Speicherblock freigegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Frei von den angegebenen Speicherblock, der zuvor von reservierten [zuweisen](#allocate) oder [erneuten](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namegetnilstringa--iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 Gibt einen Zeiger auf eine Zeichenfolge-Datenstruktur für eine leere Zeichenfolge.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CStringData` Objekt verwendet, um eine leere Zeichenfolge darzustellen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um eine Darstellung eine leere Zeichenfolge zurück.  
  
> [!NOTE]
>  Beim Implementieren eines benutzerdefinierten Zeichenfolgen-Managers muss diese Funktion nicht fehlschlagen. Sie können dies sicherstellen, indem Einbetten einer Instanz von **CNilStringData** in den String-Klasse und der Rückgabe einen Zeiger auf diese Instanz.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namereallocatea--iatlstringmgrreallocate"></a><a name="reallocate"></a>IAtlStringMgr::Reallocate  
 Ordnet eine Zeichenfolge-Datenstruktur.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Zeiger auf den Speicher, der zuvor von diesem Speichermanager zugewiesen.  
  
 `nAllocLength`  
 Die Anzahl der Zeichen in der neuen Speicherblock.  
  
 `nCharSize`  
 Die Größe (in Byte) der den Zeichentyp von Zeichenfolgen-Manager verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie die Größe des vorhandenen Speicherblocks, der durch angegebenen `pData`.  
  
 Rufen Sie [IAtlStringMgr::Free](#free) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



