---
title: 'Synclockt:: Synclockt-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3353df1a73821a2009aeba2367f1892b06aba5b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889839"
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT-Konstruktor
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `other`  
 Ein Rvalue-Verweis auf ein anderes SyncLockT-Objekt.  
  
 `sync`  
 Ein Verweis auf ein anderes SyncLockWithStatusT-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der SyncLockT-Klasse.  
  
 Der erste Konstruktor initialisiert das aktuelle SyncLockT-Objekt aus einem anderen SyncLockT-Objekt, die vom Parameter angegebenen `other`, und klicken Sie dann die anderen SyncLockT-Objekt ungültig. Der zweite Konstruktor ist `protected`, und die aktuelle SyncLockT-Objekt, das einen ungültigen Status initialisiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockT-Klasse](../windows/synclockt-class.md)