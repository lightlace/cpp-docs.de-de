---
title: 'Creatormap:: ActivationID-Datenmember | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::activationId
dev_langs:
- C++
helpviewer_keywords:
- activationId data member
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 70a331bbbf34a623b02e9d8bc9aa0b80fbee2216
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467130"
---
# <a name="creatormapactivationid-data-member"></a>CreatorMap::activationId-Datenmember
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## <a name="parameters"></a>Parameter  
 *clsid*  
 Eine Schnittstellen-ID.  
  
 *getRuntimeName*  
 Eine Funktion, die den Windows-Runtime-Namen eines Objekts abruft.  
  
## <a name="remarks"></a>Hinweise  
 Stellt eine Objekt-ID, die durch eine klassische COM-Klassen-ID oder Name einer Windows-Runtime identifiziert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [CreatorMap-Struktur](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)