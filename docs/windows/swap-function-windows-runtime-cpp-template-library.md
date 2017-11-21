---
title: Swap-Funktion (Windows Runtime C++-Vorlagenbibliothek) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::Swap
dev_langs: C++
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b48be8c5cd4702d0d4ee2dd7d541829e3bf94ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="swap-function-windows-runtime-c-template-library"></a>Swap-Funktion (C++-Vorlagenbibliothek der Windows-Runtime)
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW inline void Swap(  
   _Inout_ T& left,  
   _Inout_ T& right  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `left`  
 Das erste Argument.  
  
 `right`  
 Das zweite Argument.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="remarks"></a>Hinweise  
 Vertauscht die Werte der beiden angegebenen Argumente.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)