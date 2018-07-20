---
title: 'Module:: Create-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99ede64c239909956f1f767db34a2a6a14c02314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874888"
---
# <a name="modulecreate-method"></a>Module::Create-Methode
Erstellt eine Instanz eines Moduls.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW static Module& Create();  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<typename T>  
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

 