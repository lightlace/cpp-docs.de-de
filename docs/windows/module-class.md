---
title: "Module-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module-Klasse"
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine Auflistung verknüpfte Objekte dar.  
  
## Syntax  
  
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
  
#### Parameter  
 `moduleType`  
 Eine Kombination einem oder mehreren [ModuleType](../windows/moduletype-enumeration.md)\-Enumerationswerte.  
  
## Member  
  
### Geschützte Klassen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Module::GenericReleaseNotifier\-Klasse](../windows/module-genericreleasenotifier-class.md)|Ruft ein Ereignishandler ausgelöst, wenn das letzte Objekt im aktuellen Modul freigegeben wird.  Der Ereignishandler wird von einem Lambda\-Ausdruck, einem Funktionselement oder einer Zeiger\-zuFunktion angegeben.|  
|[Module::MethodReleaseNotifier\-Klasse](../windows/module-methodreleasenotifier-class.md)|Ruft ein Ereignishandler ausgelöst, wenn das letzte Objekt im aktuellen Modul freigegeben wird.  Der Ereignishandler wird von einem Objekt und seiner Zeiger\-zu\-einMethodenmember angegeben.|  
|[Module::ReleaseNotifier\-Klasse](../windows/module-releasenotifier-class.md)|Ruft ein Ereignishandler ausgelöst, wenn das letzte Objekt in einem Modul freigegeben wird.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Module::~Module\-Destruktor](../windows/module-tilde-module-destructor.md)|Deinitialisiert die aktuelle Instanz der Modulklasse.|  
  
### Geschützte Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Module::Module\-Konstruktor](../windows/module-module-constructor.md)|Initialisiert eine neue Instanz der Modulklasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Module::Create\-Methode](../windows/module-create-method.md)|Erstellt eine Instanz eines Moduls.|  
|[Module::DecrementObjectCount\-Methode](../windows/module-decrementobjectcount-method.md)|Dekrementiert die Anzahl von Objekten, die vom Modul nachverfolgt werden.|  
|[Module::GetActivationFactory\-Methode](../windows/module-getactivationfactory-method.md)|Ruft eine Aktivierungsfactory für das Modul aus.|  
|[Module::GetClassObject\-Methode](../windows/module-getclassobject-method.md)|Ruft einen Cache Klassenfactorys ab.|  
|[Module::GetModule\-Methode](../windows/module-getmodule-method.md)|Erstellt eine Instanz eines Moduls.|  
|[Module::GetObjectCount\-Methode](../windows/module-getobjectcount-method.md)|Ruft die Anzahl der Objekte, die von diesem Modul verwaltet werden.|  
|[Module::IncrementObjectCount\-Methode](../windows/module-incrementobjectcount-method.md)|Inkrementiert die Anzahl von Objekten, die vom Modul nachverfolgt werden.|  
|[Module::RegisterCOMObject\-Methode](../windows/module-registercomobject-method.md)|Registriert mindestens COM\-Objekte, sodass andere Anwendungen eine Verbindung herzustellen.|  
|[Module::RegisterObjects\-Methode](../windows/module-registerobjects-method.md)|Register COM\- oder [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Objekten, sodass andere Anwendungen eine Verbindung herzustellen.|  
|[Module::RegisterWinRTObject\-Methode](../windows/module-registerwinrtobject-method.md)|Registriert eine oder mehrere [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Objekte, sodass andere Anwendungen eine Verbindung herzustellen.|  
|[Module::Terminate\-Methode](../windows/module-terminate-method.md)|Bewirkt alle Factorys, die vom Modul instanziiert werden, um diese.|  
|[Module::UnregisterCOMObject\-Methode](../windows/module-unregistercomobject-method.md)|Hebt die Registrierung eine oder mehrere COM\-Objekte, das von anderen Anwendungen an der Verbindung an sie verhindert.|  
|[Module::UnregisterObjects\-Methode](../windows/module-unregisterobjects-method.md)|Hebt die Registrierung der Objekte im angegebenen Modul, damit andere Anwendungen nicht mit dieser herstellen können.|  
|[Module::UnregisterWinRTObject\-Methode](../windows/module-unregisterwinrtobject-method.md)|Hebt die Registrierung eine oder mehrere [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Objekte, sodass andere Anwendungen nicht mit dieser herstellen können.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Module::Create\-Methode](../windows/module-create-method.md)|Erstellt eine Instanz eines Moduls.|  
  
### Geschützte Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Module::objectCount\_\-Datenmember](../windows/module-objectcount-data-member.md)|Behält verfolgen, wie viele Klassen mit der Funktion [Ausführen](../windows/make-function.md) erstellt wurden.|  
|[Module::releaseNotifier\_\-Datenmember](../windows/module-releasenotifier-data-member.md)|Hält einen Zeiger auf einen ReleaseNotifier\-Objekt an.|  
  
### Makros  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|Füllt einen internen Cache auf, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen kann.  Dieses Makro gibt Standardfactory und s\-bit für Gruppe Parameter an.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|Füllt einen internen Cache auf, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen kann.  Dieses Makro ermöglicht es, einen bestimmten Factoryparameter anzugeben.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|Füllt einen internen Cache auf, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen kann.  Dieses Makro, können Sie bestimmte Factory\- und bit\- für Gruppeparametern anzugeben.|  
  
## Vererbungshierarchie  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)