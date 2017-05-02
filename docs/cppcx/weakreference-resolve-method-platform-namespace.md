---
title: "WeakReference::Resolve-Methode (Plattform-Namespace) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::Resolve"
ms.assetid: 78bbcadd-89d0-4863-a4e8-1d84040eed7d
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::Resolve-Methode (Plattform-Namespace)
Gibt einen Handle zur ursprünglichen Verweisklasse oder `nullptr` zurück, wenn das Objekt nicht mehr vorhanden ist.  
  
## Syntax  
  
```vb  
  
template<typename T>  
T^ Resolve() const  
```  
  
#### Parameter  
  
## Eigenschaftswert\/Rückgabewert  
 Ein Handle zur Verweisklasse, der das WeakReference\-Objekt bereits zugeordnet wurde, oder nullptr.  
  
## Hinweise  
  
## Beispiel  
 Dies ist die Beschreibung für ein Codebeispiel.  
  
```  
  
Bar^ bar = ref new Bar(); //use bar... if (bar != nullptr) { WeakReference wr(bar); Bar^ newReference = wr.Resolve<Bar>(); }  
```  
  
 Beachten Sie, dass der Typparameter T und nicht T^ ist.  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)