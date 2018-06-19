---
title: 'Iconverttypeimpl:: CanConvert | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs:
- C++
helpviewer_keywords:
- CanConvert method
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2f7e32fd01c932f24b617951d601ddcfe7fb5af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099887"
---
# <a name="iconverttypeimplcanconvert"></a>IConvertTypeImpl::CanConvert
Erhalten Informationen über die Verfügbarkeit von typkonvertierungen aus, auf einen Befehl oder für ein Rowset.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(CanConvert)(DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Verwendet OLE DB-Datenkonvertierung in `MSADC.DLL`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IConvertTypeImpl-Klasse](../../data/oledb/iconverttypeimpl-class.md)