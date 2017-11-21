---
title: DerefHelper-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::Details::DerefHelper
dev_langs: C++
helpviewer_keywords: DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c97a348b1f979f21edda5faf5b0c77a91ac5950a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="derefhelper-structure"></a>DerefHelper-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T  
>  
struct DerefHelper;  
  
template <  
   typename T  
>  
struct DerefHelper<T*>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein Vorlagenparameter.  
  
## <a name="remarks"></a>Hinweise  
 In einem Funktionszeiger darstellen der `T*` Template-Parameter.  
  
 DerefHelper ist in einem Ausdruck verwendet, z. B.: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`DerefType`|Der Bezeichner für den Vorlagenparameter dereferenziert `T*`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `DerefHelper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)