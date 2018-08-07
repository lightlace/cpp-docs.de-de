---
title: 'Module:: registercomobject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c997b4221dee913a6eaad55f6f114b0ad9d820e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606539"
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject-Methode
Registriert eine oder mehrere COM-Objekte an, damit andere Anwendungen eine Verbindung damit herstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
### <a name="parameters"></a>Parameter  
 *ServerName*  
 Den vollqualifizierten Namen eines Servers.  
  
 *CLSIDs*  
 Ein Array von CLSID registrieren.  
  
 *Factorys*  
 Ein Array von IUnknown-Schnittstellen, der die Objekte der Klasse, deren Verfügbarkeit veröffentlicht wird.  
  
 *Cookies*  
 Wenn der Vorgang abgeschlossen ist, Objekte ein Array von Zeigern auf Werte, die die Klasse zu identifizieren, die registriert wurden. Diese Werte werden später verwendet werden. die Registrierung aufzuheben.  
  
 *count*  
 Die Anzahl der CLSID registrieren.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK Wenn erfo; andernfalls ein HRESULT, z. B. CO_E_OBJISREG, der den Grund angibt. der Vorgang konnte nicht.  
  
## <a name="remarks"></a>Hinweise  
 Die COM-Objekte werden bei der CLSCTX_LOCAL_SERVER-Enumerator, der die Enumeration CLSCTX registriert.  
  
 Die Art der Verbindung auf die registrierten Objekte wird durch eine Kombination aus dem aktuellen angegeben *Comflag* Template-Parameter und den REGCLS_SUSPENDED-Enumerator, der die REGCLS-Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)