---
title: 'Synclockwithstatust:: Synclockwithstatust-Konstruktor | Microsoft-Dokumentation'
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
ms.openlocfilehash: 21ce2054cabf257594cb3fa376236b9a1e504a59
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647754"
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
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
  
### <a name="parameters"></a>Parameter  
 *other*  
 Ein Rvalue-Verweis auf einen anderen **SyncLockWithStatusT** Objekt.  
  
 *sync*  
 Ein Verweis auf einen anderen **SyncLockWithStatusT** Objekt.  
  
 *status*  
 Der Wert des der [Status_](../windows/synclockwithstatust-status-data-member.md) Datenmember der *andere* Parameter oder die *Sync* Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der dem **SyncLockWithStatusT** Klasse.  
  
 Der erste Konstruktor initialisiert die aktuelle **SyncLockWithStatusT** Objekt von einem anderen **SyncLockWithStatusT** vom-Parameter angegebenen *andere*, und klicken Sie dann Erklärt die andere **SyncLockWithStatusT** Objekt. Der zweite Konstruktor ist **geschützt**, und initialisiert die aktuelle **SyncLockWithStatusT** Objekt, das einen ungültigen Status.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus-Methode](../windows/synclockwithstatust-getstatus-method.md)