---
title: 'Comptr:: Releaseandgetaddressof-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32d846a1fc41596812ca6e8578f25f9ae8115182
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883798"
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