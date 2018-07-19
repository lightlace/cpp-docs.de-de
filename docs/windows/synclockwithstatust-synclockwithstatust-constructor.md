---
title: 'Synclockwithstatust:: Synclockwithstatust-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f665866a43e45d6526aa33f17c05eacebdd84aa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891349"
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `other`  
 Ein Rvalue-Verweis auf ein anderes SyncLockWithStatusT-Objekt.  
  
 `sync`  
 Ein Verweis auf ein anderes SyncLockWithStatusT-Objekt.  
  
 `status`  
 Der Wert des der [Status_](../windows/synclockwithstatust-status-data-member.md) Datenmember der `other` Parameter oder die `sync` Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der SyncLockWithStatusT-Klasse.  
  
 Der erste Konstruktor initialisiert das aktuelle SyncLockWithStatusT-Objekt aus einem anderen Parameter gemäß SyncLockWithStatusT `other`, und klicken Sie dann die anderen SyncLockWithStatusT-Objekt ungültig. Der zweite Konstruktor ist `protected`, und die aktuelle SyncLockWithStatusT-Objekt, das einen ungültigen Status initialisiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus-Methode](../windows/synclockwithstatust-getstatus-method.md)