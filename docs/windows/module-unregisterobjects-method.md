---
title: "Module::UnregisterObjects-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterObjects-Methode"
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterObjects-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hebt die Registrierung auf die Objekte im angegebenen Modul, damit andere Programme diese hergestellt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Parameter  
 `module`  
 Ein Zeiger auf ein Modul.  
  
 `serverName`  
 Eine qualifizierte Name, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn dieser Vorgang erfolgreich ist; andernfalls Fehler ein Fehler-HRESULT, das den Grund angibt diesen Vorgang.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)