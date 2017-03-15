---
title: "InvokeHelper-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::InvokeHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeHelper-Struktur"
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InvokeHelper-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename TDelegateInterface,  
   typename TCallback,  
   unsigned int argCount  
>  
struct InvokeHelper;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 0> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 1> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 2> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 3> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 4> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 5> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 6> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 7> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 8> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 9> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
```  
  
#### Parameter  
 `TDelegateInterface`  
 `TCallback`  
 Der Typ der Ereignishandlerfunktion.  
  
 `argCount`  
 Die Anzahl von Argumenten in einer InvokeHelper\-Spezialisierung.  
  
## Hinweise  
 Stellt eine Implementierung der Invoke\(\) Methode auf Grundlage der angegebenen Anzahl und den Typ von Argumenten bereit.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Traits`|Ein Synonym für die Klasse, die den Typ jedes Ereignishandlerarguments definiert.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[InvokeHelper::InvokeHelper\-Konstruktor](../windows/invokehelper-invokehelper-constructor.md)|Initialisiert eine neue Instanz der InvokeHelper\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[InvokeHelper::Invoke\-Methode](../windows/invokehelper-invoke-method.md)|Ruft den Ereignishandler auf, dessen Signatur die angegebene Anzahl von Argumenten enthält.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[InvokeHelper::callback\_\-Datenmember](../windows/invokehelper-callback-data-member.md)|Stellt den Ereignishandler dar, die aufgerufen werden soll, wenn ein Ereignis eintritt.|  
  
## Vererbungshierarchie  
 `InvokeHelper`  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)