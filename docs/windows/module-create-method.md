---
title: 'Module:: Create-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::Create
dev_langs: C++
helpviewer_keywords: Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a5d3888657d491502b13283b5b9d7141940ade3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="modulecreate-method"></a>Module::Create-Methode
Erstellt eine Instanz eines Moduls.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Modultyp.  
  
 `callback`  
 Wird aufgerufen, wenn das letzte Instanzobjekt des Moduls freigegeben wird.  
  
 `object`  
 Die `object` und `method` Parameter in Kombination verwendet werden. Zeigt bis zum letzten Instance-Objekt, wenn die letzte Instanzobjekt in das Modul freigegeben wird.  
  
 `method`  
 Die `object` und `method` Parameter in Kombination verwendet werden. Verweist auf die Methode der letzten Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Verweis auf das Modul.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
[Module-Klasse](../windows/module-class.md)

 