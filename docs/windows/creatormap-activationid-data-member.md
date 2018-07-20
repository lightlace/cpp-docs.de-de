---
title: 'Creatormap:: ActivationID-Datenmember | Microsoft Docs'
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
ms.openlocfilehash: 9c4ff889f808eda00e5b2ce426cd800678b4829f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881795"
---
# <a name="creatormapactivationid-data-member"></a>CreatorMap::activationId-Datenmember
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## <a name="parameters"></a>Parameter  
 `clsid`  
 Eine Schnittstellen-ID.  
  
 `getRuntimeName`  
 Eine Funktion, die die Windows-Runtime-Namen eines Objekts abgerufen.  
  
## <a name="remarks"></a>Hinweise  
 Stellt eine Objekt-ID, die entweder durch eine klassische COM-Klassen-ID oder der Name einer Windows-Runtime identifiziert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [CreatorMap-Struktur](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)