---
title: CComHeap-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c456aaa6f3448cf4386e0556773f2a9839702ccd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202421"
---
# <a name="ccomheap-class"></a>CComHeap-Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der COM-speicherbelegungsfunktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[Ccomheap:: Free](#free)|Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.|  
|[CComHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.|  
|[Ccomheap:: ReAllocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CComHeap` implementiert mithilfe der COM-Zuordnung-Funktionen, einschließlich genutzten speicherzuweisungsfunktionen [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree), [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize), und [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc). Die Höchstmenge an Arbeitsspeicher, die zugeordnet werden kann, ist gleich INT_MAX (2147483647) Bytes.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ATLComMem.h  
  
##  <a name="allocate"></a>  CComHeap::Allocate  
 Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nBytes*  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [ccomheap:: Free](#free) oder [ccomheap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Mithilfe von implementiert [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc).  
  
##  <a name="free"></a>  Ccomheap:: Free  
 Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *p*  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und hat keine Auswirkungen.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe von implementiert [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree).  
  
##  <a name="getsize"></a>  CComHeap::GetSize  
 Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *p*  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe des belegten Speicherblocks in Bytes zurück.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe von implementiert [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize).  
  
##  <a name="reallocate"></a>  Ccomheap:: ReAllocate  
 Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *p*  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
 *nBytes*  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [ccomheap:: Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Mithilfe von implementiert [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc).  
  
## <a name="see-also"></a>Siehe auch  
 [-Beispiel-Beispiel](../../visual-cpp-samples.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
 [Ccomheap-Klasse](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
