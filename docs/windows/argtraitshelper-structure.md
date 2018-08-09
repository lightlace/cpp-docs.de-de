---
title: ArgTraitsHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe97cc63de1f83d110e37451c1ceb91c7ad59f49
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652460"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper-Struktur
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename TDelegateInterface>  
struct ArgTraitsHelper;  
```  
  
### <a name="parameters"></a>Parameter  
 *TDelegateInterface*  
 Ein Delegat-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Hilft, die gemeinsamen Merkmale der Argumente des Delegaten definieren.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`methodType`|Ein Synonym für `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Ein Synonym für `ArgTraits<methodType>`.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ArgTraitsHelper::args-Konstante](../windows/argtraitshelper-args-constant.md)|Hilft [argtraits:: args](../windows/argtraits-args-constant.md) behalten Sie die Anzahl der Parameter der `Invoke` Methode einer Schnittstelle des Delegaten.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)