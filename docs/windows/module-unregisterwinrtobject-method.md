---
title: "Module::UnregisterWinRTObject-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterWinRTObject-Methode"
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterWinRTObject-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hebt die Registrierung eine oder mehrere [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Objekten, die andere Anwendung diese hergestellt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `cookie`  
 Ein Zeiger auf einen Wert, der das Objekt der Klasse identifiziert, dessen Registrierung aufgehoben werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)