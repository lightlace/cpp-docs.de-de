---
title: "Module::Create-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create-Methode"
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Module::Create-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Wird aufgerufen, wenn die letzte Instanzobjekt des Moduls freigegeben wird.  
  
 `object`  
 Die `object` und `method` Parameter in Kombination verwendet werden. Verweist auf die letzte Instance-Objekt, wenn das letzte Instanzobjekt im Modul freigegeben wird.  
  
 `method`  
 Die `object` und `method` Parameter in Kombination verwendet werden. Verweist auf die Methode des letzten Instance-Objekts, wenn die letzte Instanzobjekt im Modul freigegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Verweis auf das Modul.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
[Module-Klasse](../windows/module-class.md)

 