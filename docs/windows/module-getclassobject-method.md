---
title: 'Module:: GetClassObject-Methode | Microsoft Docs'
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
ms.openlocfilehash: 9205b04fc27e1c6e0e6133a08c3c2f69ffdfc314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878537"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject-Methode
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
 Klassen-ID.  
  
 `riid`  
 Schnittstellen-ID, die Sie anfordern.  
  
 `ppv`  
 Ein Zeiger auf das zurückgegebene Objekt.  
  
 `serverName`  
 Den Namen des Servers, der in beiden angegeben ist die `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, oder `ActivatableClass` Makro; oder `nullptr` der Standardservername abgerufen.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für COM, nicht die Windows-Runtime. Diese Methode macht nur IClassFactory Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)