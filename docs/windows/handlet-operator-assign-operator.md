---
title: 'Handlet:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa253bec9f150d08f699333cd5d5f6d4538fc2d6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653156"
---
# <a name="handletoperator-operator"></a>HandleT::operator=-Operator
Verschiebt den Wert des angegebenen **HandleT** -Objekt mit dem aktuellen **HandleT** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *h*  
 Ein Rvalue-Verweis auf ein Handle.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle **HandleT** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Vorgang erklärt die **HandleT** vom Parameter angegebenen Objekts *h*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)