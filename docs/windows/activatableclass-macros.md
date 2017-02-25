---
title: "ActivatableClass-Makros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ActivatableClass"
  - "ActivatableClassWithFactory"
  - "ActivatableClassWithFactoryEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivatableClassWithFactory"
  - "ActivatableClass"
  - "ActivatableClassWithFactoryEx"
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ActivatableClass-Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
ActivatableClass(  
   className  
);  
  
ActivatableClassWithFactory(  
   className,   
   factory  
);  
  
ActivatableClassWithFactoryEx(  
   className,   
   factory,   
   serverName  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `className`  
 Name der zu erstellenden Klasse.  
  
 `factory`  
 Eine Factory, die eine Instanz der angegebenen Klasse erstellen.  
  
 `serverName`  
 Ein Name, der eine Teilmenge der Factorys im Modul angibt.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie nicht diese Makros mit klassischen COM-es sei denn, Sie verwenden die `#undef` Richtlinie, um sicherzustellen, dass die **__WRL_WINRT_STRICT\_\_** Makrodefinition wird entfernt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)