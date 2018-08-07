---
title: 'MakeAllocator:: ~ MakeAllocator-Destruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- ~MakeAllocator, destructor
ms.assetid: f1299c5f-cc6b-4d4e-85d4-aee1be0e2b0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2e31f666ca6263a9b9b770261a0899bcad1bc8fd
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606308"
---
# <a name="makeallocatormakeallocator-destructor"></a>MakeAllocator::~MakeAllocator-Destruktor
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
~MakeAllocator();  
```  
  
## <a name="remarks"></a>Hinweise  
 Hebt die Initialisierung der aktuellen Instanz von der **MakeAllocator** Klasse.  
  
 Dieser Destruktor werden bei Bedarf auch den zugrunde liegenden belegten Speicher gelöscht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [MakeAllocator-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)