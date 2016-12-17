---
title: "CreateClassFactory-Funktion"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreateClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateClassFactory-Funktion"
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# CreateClassFactory-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine Factory erstellt, die Instanzen der angegebenen Klasse erzeugt.  
  
## Syntax  
  
```cpp  
  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
  
```  
  
#### Parameter  
 `flags`  
 Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)\-Enumerationswerten.  
  
 `entry`  
 Zeiger zum [CreatorMap](../windows/creatormap-structure.md), der Initialisierung und Registrierungsinformationen zum Parameter `riid` enthält.  
  
 `riid`  
 Verweis auf eine Schnittstelle ID  
  
 `ppFactory`  
 Wenn dieser Vorgang erfolgreich abgeschlossen ist, ein Zeiger auf eine Klassenfactory.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Ein Assertionsfehler wird ausgegeben, wenn Vorlagenparameter `Factory` nicht von der Schnittstelle IClassFactory abgeleitet.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::Details\-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)