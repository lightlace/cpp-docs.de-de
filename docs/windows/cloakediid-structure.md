---
title: CloakedIid-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 075694e83f4c0e2004ccc9a86b03a0f7b7ea7f78
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="cloakediid-structure"></a>CloakedIid-Struktur
Zeigt „RuntimeClass“-, „Implements“- und „ChainInterfaces“-Vorlagen an, dass auf die angegebene Schnittstelle in der IID-Liste nicht zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Schnittstelle, die ausgeblendet ist (verdeckt).  
  
## <a name="remarks"></a>Hinweise  
 Folgender Ausdruck ist ein Beispiel für die Verwendung CloakedIid: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)