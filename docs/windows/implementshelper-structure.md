---
title: ImplementsHelper-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs: C++
helpviewer_keywords: ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a51de59278e476be1e99b60ef1b0ab8a6e3f3cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelper-structure"></a>ImplementsHelper-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### <a name="parameters"></a>Parameter  
 `RuntimeClassFlagsT`  
 Ein Feld von Flags, die angibt, eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.  
  
 `ILst`  
 Eine Liste der Schnittstellen-IDs.  
  
 `IsDelegateToClass`  
 Geben Sie `true` ist die aktuelle Instanz von implementiert eine Basisklasse, von der ersten Schnittstellen-ID in `ILst`ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Implementiert die [implementiert](../windows/implements-structure.md) Struktur.  
  
 Diese Vorlage durchläuft eine Liste von Schnittstellen und fügt sie als Basisklassen auch Informationen zum Aktivieren von QueryInterface erforderlich sind.  
  
## <a name="members"></a>Member  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ImplementsHelper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz (Windows-Runtime-Bibliothek)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)