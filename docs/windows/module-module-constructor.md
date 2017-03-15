---
title: "Module::Module-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module, Konstruktor"
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::Module-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der Modul-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Konstruktor ist geschützt und kann nicht aufgerufen werden, mit dem `new` Schlüsselwort. Rufen Sie stattdessen entweder [Module:: GetModule-Methode](../windows/module-getmodule-method.md) oder [Module:: Create-Methode](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)