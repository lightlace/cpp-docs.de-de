---
title: FactoryCache-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a09128bd334fc6e0987e39eaf51c19aadce34ea
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647546"
---
# <a name="factorycache-structure"></a>FactoryCache-Struktur
Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct FactoryCache;  
```  
  
## <a name="remarks"></a>Hinweise  
 Enthält den Speicherort, der eine Klassenfactory und ein Wert, der einen registrierten wrt-identifiziert oder COM-Klassenobjekt.  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[FactoryCache::cookie-Datenmember](../windows/factorycache-cookie-data-member.md)|Enthält einen Wert an, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert, und wird später beim Aufheben der Registrierung des Objekts verwendet.|  
|[FactoryCache::factory-Datenmember](../windows/factorycache-factory-data-member.md)|Verweist auf eine Windows-Runtime oder COM-Klassenfactory.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `FactoryCache`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)