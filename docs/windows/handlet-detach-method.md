---
title: 'Handlet:: Detach-Methode | Microsoft Docs'
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
ms.openlocfilehash: 100d215099494c9b2714fd2c42dee69644a5006c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878462"
---
# <a name="handletdetach-method"></a>HandleT::Detach-Methode
Hebt die Zuordnung der aktuellen HandleT-Objekts aus der zugrunde liegende Handle.  
  
## <a name="syntax"></a>Syntax  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das zugrunde liegende Handle.  
  
## <a name="remarks"></a>Hinweise  
 Wenn dieser Vorgang abgeschlossen ist, wird die aktuelle HandleT auf einen ungültigen Zustand festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)