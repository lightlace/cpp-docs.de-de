---
title: 'CDynamicAccessor:: GetBookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
dev_langs:
- C++
helpviewer_keywords:
- GetBookmark method
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac9ea217b987f7355757fc756acc0108fca0e4a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetbookmark"></a>CDynamicAccessor::GetBookmark
Ruft das Lesezeichen für die aktuelle Zeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBookmark`  
 [out] Ein Zeiger auf die [CBookmark](../../data/oledb/cbookmark-class.md) Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen festlegen **DBPROP_IRowsetLocate** auf `VARIANT_TRUE` ein Lesezeichens abgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)