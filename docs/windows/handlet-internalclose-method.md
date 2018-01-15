---
title: 'Handlet:: Internalclose-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs: C++
helpviewer_keywords: InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c91d3a6eb2c03b70ca50b28189e4ab4530a2e3bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose-Methode
Schließt das aktuelle HandleT-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn die aktuelle HandleT erfolgreich geschlossen. andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 InternalClose() ist geschützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)