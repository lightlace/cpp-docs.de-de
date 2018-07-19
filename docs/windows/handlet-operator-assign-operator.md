---
title: 'Handlet:: Operator = | Microsoft Docs'
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
ms.openlocfilehash: 6a13e8eb7e74625e185b59816b5794b0390e95e3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873926"
---
# <a name="handletoperator-operator"></a>HandleT::operator=-Operator
Verschiebt den Wert des angegebenen HandleT-Objekts mit dem aktuellen HandleT-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Ein Rvalue-Verweis auf ein Handle.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle HandleT-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Vorgang wird vom Parameter angegebene HandleT-Objekt ungültig `h`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)