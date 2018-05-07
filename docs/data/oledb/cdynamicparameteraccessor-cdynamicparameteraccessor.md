---
title: CDynamicParameterAccessor::CDynamicParameterAccessor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 52ffd2f16211ae25bf1069ad1860dc273c1d5002
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a>CDynamicParameterAccessor::CDynamicParameterAccessor
Der Konstruktor.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor(eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>Parameter  
 `eBlobHandling`  
 Gibt an, wie die BLOB-Daten behandelt werden. Der Standardwert ist **DBBLOBHANDLING_DEFAULT**. Finden Sie unter [CDynamicAccessor:: Setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) eine Beschreibung der **DBBLOBHANDLINGENUM** Werte.  
  
 `nBlobSize`  
 Die maximale BLOB-Größe in Byte; Spaltendaten über diesem Wert werden als BLOB behandelt. Der Standardwert ist 8.000 sein. Finden Sie unter [CDynamicAccessor:: Setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) Details.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter der [CDynamicAccessor:: CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) für Weitere Informationen zum Umgang mit BLOB-Konstruktor.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)