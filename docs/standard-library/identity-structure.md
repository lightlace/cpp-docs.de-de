---
title: "identity-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std::identity"
  - "utility/std::identity"
  - "identity"
  - "std.identity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "identity-Klasse"
  - "identity-Struktur"
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# identity-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Struktur, die eine Typdefinition als Vorlagenparameter bereitstellt.  
  
## Syntax  
  
```  
template<class Type>  
   struct identity {  
      typedef Type type;  
      Type operator()(const Type& _Left) const;  
   };  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`_Left`|Der zu identifizieren Wert.|  
  
## Hinweise  
 Die Klasse enthält die Definition eines öffentlichen Typs `type`, die mit dem Vorlagenparametertyp ist.  Sie wird in Verbindung mit Vorlagenfunktion [forward](../Topic/forward.md) verwendet, um sicherzustellen, dass ein Funktionsparameter den gewünschten Typ verfügt.  
  
 Um Kompatibilität mit älterem Code, definiert die Klasse zusätzlich die Identitätsfunktion `operator()`, die das Argument `_Left` zurückgibt.  
  
## Anforderungen  
 **Header:** Hilfsprogramm \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<utility\>](../standard-library/utility.md)