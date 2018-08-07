---
title: 'Handlet:: Detach-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc11d6be992584adb1ce2075e73d080cc3a43f47
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569478"
---
# <a name="handletdetach-method"></a>HandleT::Detach-Methode
Hebt die Zuordnung der aktuellen **HandleT** Objekt aus der zugrunde liegende Handle.  
  
## <a name="syntax"></a>Syntax  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das zugrunde liegende Handle.  
  
## <a name="remarks"></a>Hinweise  
 Wenn dieser Vorgang abgeschlossen ist, die aktuelle **HandleT** auf einen ungültigen Zustand festgelegt ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)