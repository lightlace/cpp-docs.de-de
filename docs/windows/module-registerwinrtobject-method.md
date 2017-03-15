---
title: "Module::RegisterWinRTObject-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterWinRTObject-Methode"
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Module::RegisterWinRTObject-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Registriert eine oder mehrere [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] -Objekte so, dass andere Programme zugreifen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>Parameter  
 `serverName`  
 Ein Name, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.  
  
 `activatableClassIds`  
 Ein Array von aktivierbare CLSIDs registrieren.  
  
 `cookie`  
 Ein Wert, der die Objekte der Klasse identifiziert, die registriert wurden. Dieser Wert wird später verwendet, die Registrierung aufzuheben.  
  
 `count`  
 Die Anzahl der Objekte zu registrieren.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, z. B. CO_E_OBJISREG, die den Grund angibt Fehler aufgetreten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)