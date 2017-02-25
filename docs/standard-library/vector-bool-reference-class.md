---
title: "vector&lt;bool&gt;::reference-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference"
  - "std::vector<bool>::reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector<bool>-Verweisklasse"
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# vector&lt;bool&gt;::reference-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `vector<bool>::reference`\-Klasse ist eine Proxyklasse, die von der [vector\<bool\>\-Klasse](../standard-library/vector-bool-class.md) bereitgestellt wird, um `bool&` zu simulieren.  
  
## Hinweise  
 Ein simulierter Verweis ist erforderlich, da C\+\+ systemintern keine direkten Verweise auf Bits zulässt.  `vector<bool>` verwendet nur ein Bit pro Element, auf das anhand dieser Proxyklasse verwiesen werden kann.  Allerdings ist die Verweissimulation nicht vollständig, da bestimmte Zuweisungen ungültig sind.  Da die Adresse des `vector<bool>::reference`\-Objekts beispielsweise nicht akzeptiert werden kann, ist der folgende Code, der [vector\<bool\>::operator&#91;&#93;](../Topic/vector%3Cbool%3E::operator.md) verwendet, nicht richtig:  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error - do not use  
    bool& refb = vb[1];   // conversion error - do not use  
  
```  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|Kehrt den booleschen Wert eines Vektorelements um.|  
|[boolescher Operatorwert](../standard-library/vector-bool-reference-operator-bool.md)|Stellt eine implizite Konvertierung von `vector<bool>::reference` in `bool` bereit.|  
|[operator\=](../standard-library/vector-bool-reference-operator-assign.md)|Weist einen booleschen Wert einem Bit zu oder weist den Wert, der in einem Element enthalten ist, auf das verwiesen wird, einem Bit zu.|  
  
## Anforderungen  
 **Header**: \<Vektor\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<vector\>](../standard-library/vector.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)