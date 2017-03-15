---
title: "Module::UnregisterCOMObject-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterCOMObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterCOMObject-Methode"
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::UnregisterCOMObject-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hebt die Registrierung von ein oder mehrere COM-Objekte, die verhindert, dass andere Programme eine Verbindung zu ihnen herstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
#### <a name="parameters"></a>Parameter  
 `serverName`  
 (Nicht verwendeten)  
  
 `cookies`  
 Ein Array von Zeigern auf Werte, die Objekte der Klasse, deren Registrierung aufgehoben werden zu identifizieren. Das Array wurde von der [RegisterCOMObject](../windows/module-registercomobject-method.md) Methode.  
  
 `count`  
 Die Anzahl der Klassen aufgehoben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das den Grund angibt Fehler aufgetreten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)