---
title: 'Module:: registercomobject-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs: C++
helpviewer_keywords: RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2984d5950464385ea47301db356b7364707e667
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject-Methode
Registriert ein oder mehrere COM-Objekte, damit andere Anwendungen herstellen können.  
  
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
 Ein Array von IUnknown-Schnittstellen, der die Objekte der Klasse, deren Verfügbarkeit veröffentlicht wird.  
  
 `cookies`  
 Bei Abschluss des Vorgangs Objekte ein Array von Zeigern auf Werte, die die Klasse zu identifizieren, die registriert wurden. Diese Werte werden später verwendet, die Registrierung aufzuheben.  
  
 `count`  
 Die Anzahl der CLSIDs registrieren.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK Wenn Successfu; Andernfalls ist fehlgeschlagen HRESULT z. B. CO_E_OBJISREG, die den Grund angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die COM-Objekte werden mit dem Enumerator CLSCTX_LOCAL_SERVER der Enumeration CLSCTX registriert.  
  
 Der Typ der Verbindung auf die registrierte Objekte wird durch eine Kombination des aktuellen angegeben `comflag` Template-Parameter und den Enumerator REGCLS_SUSPENDED REGCLS-Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)