---
title: 'Makeallocator:: Detach-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: 78012634-2dda-4ea2-9ffe-40f105d2fe47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a269b7cbab3bba180dfc389075346db3c60e8bf0
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603367"
---
# <a name="makeallocatordetach-method"></a>MakeAllocator::Detach-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline void Detach();  
```  
  
## <a name="remarks"></a>Hinweise  
 Hebt die Zuordnung von belegten Arbeitsspeicher die [Allocate](../windows/makeallocator-allocate-method.md) Methode aus dem aktuellen **MakeAllocator** Objekt.  
  
 Wenn Sie aufrufen **Detach()**, Sie sind verantwortlich für das Löschen des Arbeitsspeichers, die bereitgestellt werden, indem die `Allocate` Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [MakeAllocator-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)