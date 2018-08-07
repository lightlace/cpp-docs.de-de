---
title: 'Handlet:: Internalclose-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a54b61902c8994397c7bd6effa74a90d43c7e512
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568640"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose-Methode
Schließt das aktuelle **HandleT** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn die aktuelle **HandleT** geschlossen wird, erfolgreich ist; andernfalls **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 **InternalClose()** ist **geschützt**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)