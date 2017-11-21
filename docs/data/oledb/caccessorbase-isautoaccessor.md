---
title: 'CAccessorBase:: Isautoaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs: C++
helpviewer_keywords: IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a08251ddf32f815390c28677f03536e1c2cec7d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
Gibt "true" zurück, wenn die Daten automatisch für die Zugriffsmethode bei einem Verschiebevorgang abgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Zahl 0 (null)-Offset für den Accessor.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn der Accessor ein Autoaccessor ist. Andernfalls wird **false**zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CAccessorBase-Klasse](../../data/oledb/caccessorbase-class.md)