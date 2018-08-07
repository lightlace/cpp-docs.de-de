---
title: 'Module:: GetClassObject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63ff6c63702cda709f4431d9c7e5be5a4bdb8449
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602652"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject-Methode
Ruft einen Cache von Klassenfactorys.  
  
## <a name="syntax"></a>Syntax  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *clsid*  
 Klassen-ID.  
  
 *riid*  
 Schnittstellen-ID, die Sie anfordern.  
  
 *ppv*  
 Zeiger auf das zurückgegebene Objekt.  
  
 *ServerName*  
 Den Namen des Servers, der entweder angegeben ist die `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, oder `ActivatableClass` Makro; oder **"nullptr"** um den Standardnamen für den Server zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für COM, nicht die Windows-Runtime. Diese Methode macht nur `IClassFactory` Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)