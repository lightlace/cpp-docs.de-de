---
title: 'Verifyinheritancehelper:: Verify-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04bf01b5fad5a9fec579e347497a28b5e8abb861
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018815"
---
# <a name="verifyinheritancehelperverify-method"></a>VerifyInheritanceHelper::Verify-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
static void Verify();  
```  
  
## <a name="remarks"></a>Hinweise  
 Testet die beiden Schnittstellen, die durch die aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.  
  
 Ein Fehler wird ausgegeben, wenn eine Schnittstelle nicht von der anderen abgeleitet ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [VerifyInheritanceHelper-Struktur](../windows/verifyinheritancehelper-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)