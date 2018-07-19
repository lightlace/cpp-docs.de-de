---
title: 'Synclockwithstatust:: IsLocked-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a564c4223b09d9295ff0ac3159e165944c4d885d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892552"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt an, ob das aktuelle SyncLockWithStatusT-Objekt eine Ressource besitzt. SyncLockWithStatusT-Objekt ist *gesperrt*.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** ist das SyncLockWithStatusT-Objekt gesperrt ist, andernfalls **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)