---
title: 'CAccessorBase:: Gethaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs: C++
helpviewer_keywords: GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ba60cb6dd108b0ea451baabf5941caeead11a42f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
Ruft die Accessorhandle für einen angegebenen Accessor ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HACCESSOR GetHAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Zahl 0 (null)-Offset für den Accessor.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Accessorhandle.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CAccessorBase-Klasse](../../data/oledb/caccessorbase-class.md)