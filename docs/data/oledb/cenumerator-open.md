---
title: 'CEnumerator:: Open | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 04e6884b27f45ee86085c1b820376ed087ae68c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096924"
---
# <a name="cenumeratoropen"></a>CEnumerator::Open
Den Moniker für den Enumerator Bindet, wenn eine angegeben wurde, ruft das Rowset für den Enumerator ab, durch den Aufruf [ISourcesRowset:: GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Open(LPMONIKER pMoniker) throw();  


HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();  


HRESULT Open(const CEnumerator& enumerator) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMoniker`  
 [in] Ein Zeiger auf ein Moniker ist für ein Enumerator.  
  
 *pClsid*  
 [in] Ein Zeiger auf die **CLSID** eines Enumerators.  
  
 `enumerator`  
 [in] Ein Verweis auf ein Enumerator.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CEnumerator-Klasse](../../data/oledb/cenumerator-class.md)