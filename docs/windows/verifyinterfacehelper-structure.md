---
title: VerifyInterfaceHelper-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::VerifyInterfaceHelper
dev_langs: C++
helpviewer_keywords: VerifyInterfaceHelper structure
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 51e18940786af52b86d17f2b54d6fe835c639904
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper-Struktur
Unterstützt die Windows Runtime C++ Template Library-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   bool isWinRTInterface,  
   typename I  
>  
struct VerifyInterfaceHelper;  
  
template <  
   typename I  
>  
struct VerifyInterfaceHelper<false, I>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `I`  
 Eine Schnittstelle zu überprüfen.  
  
 `isWinRTInterface`  
  
## <a name="remarks"></a>Hinweise  
 Überprüft, ob die Schnittstelle mit dem Vorlagenparameter angegebene bestimmte Anforderungen erfüllt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[VerifyInterfaceHelper::Verify-Methode](../windows/verifyinterfacehelper-verify-method.md)||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `VerifyInterfaceHelper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)