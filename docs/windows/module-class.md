---
title: Module-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
dev_langs:
- C++
helpviewer_keywords:
- Module class
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d17e0dc79241fbd84e282b9cd8403259e34def0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="module-class"></a>Module-Klasse
Stellt eine Auflistung von zugehörigen Objekten dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template<  
   ModuleType moduleType  
>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleType`  
 Eine Kombination aus einem oder mehreren [ModuleType](../windows/moduletype-enumeration.md) Enumerationswerte.  
  
## <a name="members"></a>Member  
  
### <a name="protected-classes"></a>Geschützte Klassen  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier-Klasse](../windows/module-genericreleasenotifier-class.md)|Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird auf ein Lambda, Funktionselement oder Zeiger-auf-Funktion von angegeben.|  
|[Module::MethodReleaseNotifier-Klasse](../windows/module-methodreleasenotifier-class.md)|Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird von einem Objekt und seinem Member Zeiger-zu-Methode angegeben.|  
|[Module::ReleaseNotifier-Klasse](../windows/module-releasenotifier-class.md)|Ruft einen Ereignishandler auf, wenn das letzte Objekt in einem Modul freigegeben wird.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::~Module-Destruktor](../windows/module-tilde-module-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der Module-Klasse.|  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::Module-Konstruktor](../windows/module-module-constructor.md)|Initialisiert eine neue Instanz der Module-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::Create-Methode](../windows/module-create-method.md)|Erstellt eine Instanz eines Moduls.|  
|[Module::DecrementObjectCount-Methode](../windows/module-decrementobjectcount-method.md)|Verringert die Anzahl der Objekte vom Modul nachverfolgt.|  
|[Module::GetActivationFactory-Methode](../windows/module-getactivationfactory-method.md)|Ruft eine aktivierungsfactory für das Modul an.|  
|[Module::GetClassObject-Methode](../windows/module-getclassobject-method.md)|Ermittelt einen Cache von Klassenfactorys.|  
|[Module::GetModule-Methode](../windows/module-getmodule-method.md)|Erstellt eine Instanz eines Moduls.|  
|[Module::GetObjectCount-Methode](../windows/module-getobjectcount-method.md)|Ruft die Anzahl von Objekten, die von diesem Modul verwaltet.|  
|[Module::IncrementObjectCount-Methode](../windows/module-incrementobjectcount-method.md)|Erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.|  
|[Module::RegisterCOMObject-Methode](../windows/module-registercomobject-method.md)|Registriert ein oder mehrere COM-Objekte, damit andere Anwendungen herstellen können.|  
|[Module::RegisterObjects-Methode](../windows/module-registerobjects-method.md)|Registriert COM oder Windows-Runtime-Objekte an, damit andere Anwendungen herstellen können.|  
|[Module::RegisterWinRTObject-Methode](../windows/module-registerwinrtobject-method.md)|Registriert ein oder mehrere Windows-Runtime-Objekte an, damit andere Anwendungen herstellen können.|  
|[Module::Terminate-Methode](../windows/module-terminate-method.md)|Bewirkt, dass alle Factorys instanziiert, indem das Modul heruntergefahren.|  
|[Module::UnregisterCOMObject-Methode](../windows/module-unregistercomobject-method.md)|Hebt die Registrierung auf ein oder mehrere COM-Objekte, wird verhindert, dass andere Anwendungen eine Verbindung zu ihnen herstellen.|  
|[Module::UnregisterObjects-Methode](../windows/module-unregisterobjects-method.md)|Hebt die Registrierung auf die Objekte im angegebenen Modul, damit andere Clientanwendungen auf sie keine Verbindung herstellen können.|  
|[Module::UnregisterWinRTObject-Methode](../windows/module-unregisterwinrtobject-method.md)|Hebt die Registrierung auf ein oder mehrere Windows-Runtime-Objekte, damit andere Clientanwendungen auf sie keine Verbindung herstellen können.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::Create-Methode](../windows/module-create-method.md)|Erstellt eine Instanz eines Moduls.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Module::objectCount_-Datenmember](../windows/module-objectcount-data-member.md)|Hält den Überblick über wie viele Klassen erstellt wurden die [stellen](../windows/make-function.md) Funktion.|  
|[Module::releaseNotifier_-Datenmember](../windows/module-releasenotifier-data-member.md)|Enthält einen Zeiger auf ein ReleaseNotifier-Objekt.|  
  
### <a name="macros"></a>Makros  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können. Dieses Makro gibt Factory und Gruppen-ID Standardparameter.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können. Mit diesem Makro können Sie einen bestimmten Factory-Parameter angeben.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können. Mit diesem Makro können Sie bestimmte Factory und Gruppen-ID-Parameter angeben.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)