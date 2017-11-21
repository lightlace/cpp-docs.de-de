---
title: 'Handlet:: Detach-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b17d9f720d2fee92cfcf2aaf7b9f452cde32e3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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