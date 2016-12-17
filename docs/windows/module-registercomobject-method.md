---
title: "Module::RegisterCOMObject-Methode"
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
  - "module/Microsoft::WRL::Module::RegisterCOMObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterCOMObject-Methode"
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Module::RegisterCOMObject-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein oder mehrere COM-Objekte registriert, damit andere Programme zugreifen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `serverName`  
 Den vollqualifizierten Namen eines Servers.  
  
 `clsids`  
 Ein Array von CLSIDs registrieren.  
  
 `factories`  
 Ein Array von IUnknown Schnittstellen die Objekte der Klasse, deren Verfügbarkeit veröffentlicht wird.  
  
 `cookies`  
 Wenn der Vorgang abgeschlossen ist, Objekte ein Array von Zeigern auf Werte, die die Klasse zu identifizieren, die registriert wurden. Diese Werte werden später verwendet, die Registrierung aufzuheben.  
  
 `count`  
 Die Anzahl der CLSIDs registrieren.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK Wenn Successfu; andernfalls ein HRESULT wie z. B. CO_E_OBJISREG, die den Grund angibt Fehler aufgetreten.  
  
## <a name="remarks"></a>Hinweise  
 Die COM-Objekte werden mit dem Enumerator CLSCTX_LOCAL_SERVER der Enumeration CLSCTX registriert.  
  
 Die Art der Verbindung auf die registrierten Objekte wird angegeben, indem eine Kombination des aktuellen `comflag` Vorlagenparameter und den Enumerator REGCLS_SUSPENDED REGCLS-Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)