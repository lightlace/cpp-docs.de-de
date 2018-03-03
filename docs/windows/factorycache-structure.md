---
title: FactoryCache-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0fc48c9a3651e8c5a6609886862c2f73c5707638
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="factorycache-structure"></a>FactoryCache-Struktur
Unterstützt die Windows Runtime C++ Template Library-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct FactoryCache;  
```  
  
## <a name="remarks"></a>Hinweise  
 Enthält den Speicherort einer Klassenfactory und ein Wert, der einem registrierten wrt identifiziert oder COM-Klassenobjekt.  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[FactoryCache::cookie-Datenmember](../windows/factorycache-cookie-data-member.md)|Enthält einen Wert, der ein registrierten Windows-Runtime oder COM-Klassenobjekt bezeichnet und wird später verwendet werden, um stattdessen das Aufheben der Registrierung.|  
|[FactoryCache::factory-Datenmember](../windows/factorycache-factory-data-member.md)|Verweist auf ein Windows-Runtime oder COM-Klassenfactory.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `FactoryCache`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)