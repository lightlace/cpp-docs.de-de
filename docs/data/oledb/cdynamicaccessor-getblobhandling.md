---
title: 'CDynamicAccessor:: Getblobhandling | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
dev_langs: C++
helpviewer_keywords: GetBlobHandling method
ms.assetid: bbc6dda6-e132-42a3-980d-24e455cbe456
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b9bac84019f408c7a68cf6afbffe94572be44c46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetblobhandling"></a>CDynamicAccessor::GetBlobHandling
Ruft das BLOB Behandlung von Wert für die aktuelle Zeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
const DBBLOBHANDLINGENUM GetBlobHandling( ) const;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt die Behandlung von Wert BLOB `eBlobHandling` entsprechend der Festlegung durch [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)