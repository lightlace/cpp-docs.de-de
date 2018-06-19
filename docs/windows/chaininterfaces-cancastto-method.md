---
title: 'Chaininterfaces:: Cancastto-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2286c347fbd68f34fac807e80facca0a0286aa6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860293"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo-Methode
Gibt an, ob die angegebene Schnittstellen-ID in jeweils die durch die Vorlagenparameter nicht standardmäßiger definiert spezialisierungen umgewandelt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Eine Schnittstellen-ID.  
  
 `ppv`  
 Ein Zeiger auf die letzte Schnittstellen-ID, die erfolgreich umgewandelt wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn alle Umwandlungsvorgänge erfolgreich war; andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)