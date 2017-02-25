---
title: "CreateActivationFactory-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreateActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateActivationFactory-Funktion"
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# CreateActivationFactory-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine Factory erstellt, die Instanzen der angegebenen Klasse erzeugt, die von der Runtime Windows aktiviert werden kann.  
  
## Syntax  
  
```cpp  
  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,    
      _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
  
```  
  
#### Parameter  
 `flags`  
 Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)\-Enumerationswerten.  
  
 `entry`  
 Zeiger zum [CreatorMap](../windows/creatormap-structure.md), der Initialisierung und Registrierungsinformationen zum Parameter `riid` enthält.  
  
 `riid`  
 Verweis auf eine Schnittstelle ID  
  
 `ppFactory`  
 Wenn dieser Vorgang erfolgreich abgeschlossen ist, ein Zeiger auf eine Aktivierungsfactory.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Ein Assertionsfehler wird ausgegeben, wenn Vorlagenparameter `Factory` nicht von der Schnittstelle IActivationFactory abgeleitet.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::Details\-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)