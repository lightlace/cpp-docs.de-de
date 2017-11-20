---
title: 'CDBPropSet:: SetGuid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs: C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca1d8b4b6ee46f7debb52a6ebd0bbfbeded1fede
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
Legt die **GuidPropertySet** -Feld in der **DBPROPSET** Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 [in] Eine GUID zum Festlegen der **GuidPropertySet** Feld der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Feld kann festgelegt werden, indem Sie die [Konstruktor](../../data/oledb/cdbpropset-cdbpropset.md) ebenfalls.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDBPropSet-Klasse](../../data/oledb/cdbpropset-class.md)