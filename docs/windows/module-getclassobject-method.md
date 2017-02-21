---
title: "Module::GetClassObject-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetClassObject-Methode"
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::GetClassObject-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt einen Cache von Klassenfactorys.  
  
## <a name="syntax"></a>Syntax  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `clsid`  
 Klassen-ID  
  
 `riid`  
 Schnittstellen-ID, die Sie anfordern.  
  
 `ppv`  
 Ein Zeiger auf das zurückgegebene Objekt.  
  
 `serverName`  
 Den Namen des Servers, der in beiden angegeben ist die `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, oder `ActivatableClass` Makro; oder `nullptr` Der Standardservername abgerufen.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für COM, nicht die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]. Diese Methode macht nur IClassFactory-Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)