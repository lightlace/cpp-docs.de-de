---
title: 'Argtraits:: args-Konstante | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f87b29634d5b9acef2e2ccb3f7b4d5f227433d38
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855772"
---
# <a name="argtraitsargs-constant"></a>ArgTraits::args-Konstante
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
static const int args = -1; ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Behält die Anzahl von Parametern auf die Invoke-Methode einer Schnittstelle des Delegaten.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `args` gleich-1 gibt an, es kann keine Übereinstimmung für die Invoke-Methodensignatur.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ArgTraits-Struktur](../windows/argtraits-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)