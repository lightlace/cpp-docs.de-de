---
title: 'Srwlockexclusivetraits:: Unlock-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ac40ea65dad74d42a3ee729bfb1cd1711879a06
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="srwlockexclusivetraitsunlock-method"></a>SRWLockExclusiveTraits::Unlock-Methode
Gibt die exklusive Kontrolle über das angegebene SRWLock-Objekt frei.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `srwlock`  
 Handle für ein SRWLock-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [SRWLockExclusiveTraits-Struktur](../windows/srwlockexclusivetraits-structure.md)