---
title: 'Chaininterfaces:: Verify-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c83479434a936f32fb0f7367d8cd02c6676c74e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify-Methode
Stellt sicher, dass jede Schnittstelle durch den Vorlagenparameter definiert `I0` über `I9` erbt von IUnknown und/oder "iinspectable", und dass `I0` erbt von `I1` über `I9`.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Überprüfungsvorgang fehlschlägt, eine `static_assert` gibt eine Fehlermeldung, die den Fehler beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Vorlagenparameter `I0` und `I1` sind erforderlich, und die Parameter `I2` über `I9` sind optional.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)