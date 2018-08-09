---
title: IsBaseOfStrict-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4690c15adac7be66ca916b1fc0f769e6c50190c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017899"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict-Struktur
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
### <a name="parameters"></a>Parameter  
 *Basis*  
 Der Basistyp.  
  
 *Abgeleitete*  
 Der abgeleitete Typ.  
  
## <a name="remarks"></a>Hinweise  
 Testet, ob ein Typ die Basis eines anderen ist.  
  
 Die erste Vorlage testet, ob ein Typ von einem Basistyp abgeleitet ist, die ergeben können **"true"** oder **"false"**. Die zweite Vorlage testet, ob ein Typ von sich selbst zu abgeleitet ist, die führt zu immer **"false"**.  
  
## <a name="members"></a>Member  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[IsBaseOfStrict::value-Konstante](../windows/isbaseofstrict-value-constant.md)|Gibt an, ob ein Typ die Basis eines anderen ist.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)