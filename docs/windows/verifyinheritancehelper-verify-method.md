---
title: 'Verifyinheritancehelper:: Verify-Methode | Microsoft Docs'
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
ms.openlocfilehash: 879f5fa117f0f2bc444243f540925d64a2b824b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889874"
---
# <a name="verifyinheritancehelperverify-method"></a>VerifyInheritanceHelper::Verify-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
static void Verify();  
```  
  
## <a name="remarks"></a>Hinweise  
 Testet die beiden Schnittstellen, die durch den aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.  
  
 Ein Fehler wird ausgegeben, wenn eine Schnittstelle nicht von der anderen abgeleitet ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [VerifyInheritanceHelper-Struktur](../windows/verifyinheritancehelper-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)