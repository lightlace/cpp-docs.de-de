---
title: 'Iconverttypeimpl:: CanConvert | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs: C++
helpviewer_keywords: CanConvert method
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fcb5870fc1c66fed6657e342c8aea119fa727fcf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="iconverttypeimplcanconvert"></a>IConvertTypeImpl::CanConvert
Erhalten Informationen über die Verfügbarkeit von typkonvertierungen aus, auf einen Befehl oder für ein Rowset.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Verwendet OLE DB-Datenkonvertierung in `MSADC.DLL`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IConvertTypeImpl-Klasse](../../data/oledb/iconverttypeimpl-class.md)