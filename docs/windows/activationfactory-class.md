---
title: "ActivationFactory-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactory-Klasse"
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ActivationFactory-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aktiviert eine oder mehrere von der Windows Runtime zu aktivierenden Klassen.  
  
## Syntax  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### Parameter  
 `I0`  
 Die zeroth Schnittstelle.  
  
 `I1`  
 Die erste Schnittstelle.  
  
 `I2`  
 Die zweite Schnittstelle.  
  
## Hinweise  
 ActivationFactory stellt Registrierungsmethoden und \-grundlegende Funktionen für die IActivationFactory\-Schnittstelle bereit.  ActivationFactory können Sie auch, um eine benutzerdefinierte Factoryimplementierung bereitzustellen.  
  
 Das folgende Codefragment veranschaulicht symbolisch, wie ActivationFactory verwendet.  
  
 [!CODE [wrl-microsoft__wrl__activationfactory#1](../CodeSnippet/VS_Snippets_Misc/wrl-microsoft__wrl__activationfactory#1)]  
  
 Das folgende Codefragment zeigt, wie die [Implementiert](../windows/implements-structure.md)\-Struktur verwendet, um mehr als drei Schnittstellen\-IDs anzugeben.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ActivationFactory::ActivationFactory\-Konstruktor](../windows/activationfactory-activationfactory-constructor.md)|Initialisiert die ActivationFactory\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ActivationFactory::AddRef\-Methode](../windows/activationfactory-addref-method.md)|Inkrementiert den Verweiszählerwert des aktuellen ActivationFactory\-Objekts.|  
|[ActivationFactory::GetIids\-Methode](../windows/activationfactory-getiids-method.md)|Ruft ein Array implementierte Schnittstellen\-IDs ab.|  
|[ActivationFactory::GetRuntimeClassName\-Methode](../windows/activationfactory-getruntimeclassname-method.md)|Ruft den Ablaufklassennamen des Objekts, das der aktuelle ActivationFactory instanziiert.|  
|[ActivationFactory::GetTrustLevel\-Methode](../windows/activationfactory-gettrustlevel-method.md)|Ruft die Vertrauensebene des Objekts, das der aktuelle ActivationFactory instanziiert.|  
|[ActivationFactory::QueryInterface\-Methode](../windows/activationfactory-queryinterface-method.md)|Ruft einen Zeiger auf die angegebene Schnittstelle ab.|  
|[ActivationFactory::Release\-Methode](../windows/activationfactory-release-method.md)|Dekrementiert den Verweiszählerwert des aktuellen ActivationFactory\-Objekts.|  
  
## Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)