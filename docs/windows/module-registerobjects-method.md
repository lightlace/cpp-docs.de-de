---
title: "Module::RegisterObjects-Methode"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterObjects-Methode"
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Module::RegisterObjects-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM registriert oder [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Objekte so, dass andere Programme zugreifen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Parameter  
 `module`  
 Ein Array von COM- oder [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] Objekte.  
  
 `serverName`  
 Der Name des Servers, der die Objekte erstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; ein HRESULT, das den Grund angibt konnte, andernfalls der Vorgang.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)