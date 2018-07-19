---
title: 'Semaphoretraits:: Unlock-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0914c6ff83e881f92963fc8a548ddeff587db75e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892246"
---
# <a name="semaphoretraitsunlock-method"></a>SemaphoreTraits::Unlock-Methode
Versionen Kontrolle über eine freigegebene Ressource.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Handle für einen Semaphorobjekt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Unlock-Vorgang nicht erfolgreich ist, gibt Unlock() einen Fehler, der die Ursache des Fehlers angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [SemaphoreTraits-Struktur](../windows/semaphoretraits-structure.md)