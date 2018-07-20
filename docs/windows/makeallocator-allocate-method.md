---
title: 'Makeallocator:: Allocate-Methode | Microsoft Docs'
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
ms.openlocfilehash: d0e8d387dea7687ad61d85f975d58aa47489266d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876215"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg, ein Zeiger auf den belegten Speicher; andernfalls `nullptr`.  
  
## <a name="remarks"></a>Hinweise  
 Belegt Speicher aus, und ordnet dieses dem aktuellen MakeAllocator-Objekt.  
  
 Die Größe des belegten ist die Größe des Typs mit dem aktuellen MakeAllocator-Vorlagenparameter angegeben.  
  
 Ein Entwickler muss nur die Allocate()-Methode, um eine andere Zuordnung Speichermodell implementieren außer Kraft setzen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [MakeAllocator-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)