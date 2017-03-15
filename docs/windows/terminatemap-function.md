---
title: "TerminateMap-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::TerminateMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TerminateMap-Funktion"
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TerminateMap-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>Parameter  
 `module`  
 Ein [Modul](../windows/module-class.md).  
  
 `serverName`  
 Der Name einer Teilmenge von Klassenfactorys im Parameter angegebenen Modul `module`.  
  
 `forceTerminate`  
 `true` So beenden die Klasse sind Factorys unabhängig von der sie aktiv; `false` Klassenfactorys nicht beendet, wenn alle Factory aktiv ist.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn alle Klassenfactorys beendet wurden. andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Fährt den Klassenfactorys im angegebenen Modul.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)