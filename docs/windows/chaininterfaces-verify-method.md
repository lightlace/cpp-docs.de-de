---
title: 'Chaininterfaces:: Verify-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: a845ea047682fda97ae581f4daad26775241ddf8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466838"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify-Methode
Stellt sicher, dass jede Schnittstelle Vorlagenparameter definiert *I0* über *I9* erbt von IUnknown und/oder "iinspectable", und dass *I0* erbt von *I1* über *I9*.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Überprüfungsvorgang fehlschlägt, eine **"static_assert"** gibt eine Fehlermeldung, die den Fehler beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Vorlagenparameter *I0* und *I1* sind erforderlich, und die Parameter *I2* über *I9* sind optional.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)