---
title: 'Makeallocator:: Allocate-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3252096216757c34e93933bcdd91f9da2c5bb14f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015968"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg einen Zeiger auf den reservierten Speicher; andernfalls **"nullptr"**.  
  
## <a name="remarks"></a>Hinweise  
 Weist Speicher zu und ordnet es die aktuellen **MakeAllocator** Objekt.  
  
 Die Größe des zugeordneten Speichers ist die Größe des vom aktuellen angegebenen Typs **MakeAllocator** Template-Parameter.  
  
 Ein Entwickler benötigt, um nur überschreiben die **Allocate()** zu einer anderen Zuordnung Speichermodell zu implementierende Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [MakeAllocator-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)