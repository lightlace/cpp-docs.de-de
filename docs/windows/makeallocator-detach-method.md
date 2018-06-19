---
title: 'Makeallocator:: Detach-Methode | Microsoft Docs'
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
ms.openlocfilehash: 50afca04492c29aa526f7a004c6e0f725022e9ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876968"
---
# <a name="makeallocatordetach-method"></a>MakeAllocator::Detach-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline void Detach();  
```  
  
## <a name="remarks"></a>Hinweise  
 Hebt die Zuordnung von belegten Arbeitsspeicher die [Allocate](../windows/makeallocator-allocate-method.md) Methode aus dem aktuellen MakeAllocator-Objekt.  
  
 Wenn Sie Detach() aufrufen, sind Sie verantwortlich für das Löschen des Arbeitsspeichers, die von der Allocate-Methode bereitgestellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [MakeAllocator-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)