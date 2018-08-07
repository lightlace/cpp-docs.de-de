---
title: IsSame-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
dev_langs:
- C++
helpviewer_keywords:
- IsSame structure
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc770ce418f458109ab2b047a5bb0f7e006ae499
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603584"
---
# <a name="issame-structure"></a>IsSame-Struktur
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
### <a name="parameters"></a>Parameter  
 *T1*  
 Ein Typ.  
  
 *T2*  
 Einen anderen Typ.  
  
## <a name="remarks"></a>Hinweise  
 Überprüft, ob es sich bei einem Typ angegeben ist identisch mit einer anderen angegebenen Typ.  
  
## <a name="members"></a>Member  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[IsSame::value-Konstante](../windows/issame-value-constant.md)|Gibt an, ob ein Typ mit einer anderen identisch ist.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IsSame`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)