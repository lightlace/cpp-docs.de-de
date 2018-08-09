---
title: HANDLENullTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
dev_langs:
- C++
helpviewer_keywords:
- HANDLENullTraits structure
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e009b31f95f2cdf80231021c38848fbc30ce20d3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645437"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits-Struktur
Definiert die allgemeinen Merkmale eines nicht initialisierten Handles.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct HANDLENullTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Type`|Ein Synonym für den HANDLE.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HANDLENullTraits::Close-Methode](../windows/handlenulltraits-close-method.md)|Schließt das angegebene Handle.|  
|[HANDLENullTraits::GetInvalidValue-Methode](../windows/handlenulltraits-getinvalidvalue-method.md)|Stellt ein ungültiges Handle dar.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HANDLENullTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)