---
title: SRWLockExclusiveTraits-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b5d56c4e0c31b56e5bdc92a9d209b58cd15ffb1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889276"
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