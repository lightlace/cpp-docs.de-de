---
title: 'Chaininterfaces:: Cancastto-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99738f9c5335ede5dafe60e35b3104951f5fb556
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 `true`Wenn alle Umwandlungsvorgänge erfolgreich war; andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)