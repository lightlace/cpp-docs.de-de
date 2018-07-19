---
title: SRWLockSharedTraits-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a18edef3fa658608459244143a5e48738f0c3a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889634"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits-Struktur
Beschreibt allgemeine Merkmale der SRWLock-Klasse in freigegebene Sperren an.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Type`|Synonym für einen Zeiger auf die [SRWLOCK](../windows/srwlock-class.md) Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue-Methode](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Ruft ein SRWLockSharedTraits-Objekt, das immer ungültig ist.|  
|[SRWLockSharedTraits::Unlock-Methode](../windows/srwlocksharedtraits-unlock-method.md)|Gibt die exklusive Kontrolle über das angegebene SRWLock-Objekt frei.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)