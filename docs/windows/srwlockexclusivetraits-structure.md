---
title: SRWLockExclusiveTraits-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs: C++
helpviewer_keywords: SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05e7b2a6814cefffee258909f4bab11fcfe34f1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits-Struktur
Beschreibt allgemeine Eigenschaften des SRWLock-Klasse, im Sperrmodus für exklusive.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Type`|Synonym für einen Zeiger auf die [SRWLOCK](../windows/srwlock-class.md) Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue-Methode](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Ruft ein SRWLockExclusiveTraits-Objekt, das immer ungültig ist.|  
|[SRWLockExclusiveTraits::Unlock-Methode](../windows/srwlockexclusivetraits-unlock-method.md)|Gibt die exklusive Kontrolle über das angegebene SRWLock-Objekt frei.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)