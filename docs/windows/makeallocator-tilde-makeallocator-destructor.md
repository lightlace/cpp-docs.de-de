---
title: 'MakeAllocator:: ~ MakeAllocator-Destruktor | Microsoft Docs'
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
ms.openlocfilehash: f0734f895315f1c8ba7577d531c54a9dc11381e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877098"
---
# <a name="makeallocatormakeallocator-destructor"></a>MakeAllocator::~MakeAllocator-Destruktor
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
~MakeAllocator();  
```  
  
## <a name="remarks"></a>Hinweise  
 Hebt die Initialisierung der aktuellen Instanz der MakeAllocator-Klasse.  
  
 Dieser Destruktor werden bei Bedarf auch den zugrunde liegenden belegten Speicher gelöscht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [MakeAllocator-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)