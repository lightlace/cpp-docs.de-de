---
title: 'Activationfactory:: Gettrustlevel-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs: C++
helpviewer_keywords: GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 48db1632c50726073372e314a338cdca543c29e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel-Methode
Ruft die Vertrauensebene des Objekts, das den aktuellen ActivationFactory instanziiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Parameter  
 `trustLvl`  
 Wenn dieser Vorgang abgeschlossen wird, die Vertrauensebene der Common Language Runtime-Klasse, die die ActivationFactory instanziiert.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Andernfalls wird ein Assertionsfehler ausgegeben und `trustLvl` auf FullTrust festgelegt ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ActivationFactory-Klasse](../windows/activationfactory-class.md)