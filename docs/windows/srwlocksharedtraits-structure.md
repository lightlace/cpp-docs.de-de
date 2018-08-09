---
title: SRWLockSharedTraits-Struktur | Microsoft-Dokumentation
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
ms.openlocfilehash: c606a1a7d32a02442e767a31543a76a4dccf295e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652473"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits-Struktur
Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse in freigegebene sperren.  
  
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
|[SRWLockSharedTraits::GetInvalidValue-Methode](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Ruft eine **SRWLockSharedTraits** -Objekt, das immer ungültig ist.|  
|[SRWLockSharedTraits::Unlock-Methode](../windows/srwlocksharedtraits-unlock-method.md)|Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)