---
title: 'Comptr:: Releaseandgetaddressof-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be56e7afb23295e9b03d801943af25c652d18758
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf-Methode
Gibt die Schnittstelle frei, die diesem ComPtr-Objekt zugeordnet ist, und ruft dann die Adresse des [ptr_](../windows/comptr-ptr-data-member.md) -Datenmembers ab, der einen Zeiger auf die Schnittstelle enthält, die freigegeben wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die Adresse der [Ptr_](../windows/comptr-ptr-data-member.md) Datenmember der dieses comptr-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)   
 [ComPtr::ptr_-Datenmember](../windows/comptr-ptr-data-member.md)