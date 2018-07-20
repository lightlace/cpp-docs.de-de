---
title: IsBaseOfStrict-Struktur | Microsoft Docs
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
ms.openlocfilehash: db8f315c0589ceb7cd9411873152fe644985818e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876890"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Der Basistyp.  
  
 `Derived`  
 Der abgeleitete Typ.  
  
## <a name="remarks"></a>Hinweise  
 Testet, ob ein Typ die Basis eines anderen ist.  
  
 Die erste Vorlage testet, ob ein Typ von einem Basistyp abgeleitet ist ergeben **"true"** oder **"false"**. Die zweite Vorlage testet, ob ein Typ von sich selbst zu abgeleitet ist, ergibt immer **"false"**.  
  
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