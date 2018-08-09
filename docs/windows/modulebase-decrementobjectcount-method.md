---
title: 'Modulebase:: Decrementobjectcount-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- DecrementObjectCount method
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65dc4dbca2e152a62bb79ed104f9533d2fa20569
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019981"
---
# <a name="modulebasedecrementobjectcount-method"></a>ModuleBase::DecrementObjectCount-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
virtual long DecrementObjectCount() = 0;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl der vor der dekrementvorgang werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ModuleBase-Klasse](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)