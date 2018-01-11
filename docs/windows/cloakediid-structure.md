---
title: CloakedIid-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::CloakedIid
dev_langs: C++
helpviewer_keywords: CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c61e005759af9b5fde4bfff407ed502a41c22a72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cloakediid-structure"></a>CloakedIid-Struktur
Zeigt „RuntimeClass“-, „Implements“- und „ChainInterfaces“-Vorlagen an, dass auf die angegebene Schnittstelle in der IID-Liste nicht zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename T  
>  
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