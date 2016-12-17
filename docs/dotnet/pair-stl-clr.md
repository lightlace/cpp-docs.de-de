---
title: "pair (STL/CLR)"
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
  - "cliext::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair-Klasse [STL/CLR]"
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das einem Wertpaar umschließt.  
  
## Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### Parameter  
 Value1  
 Der Typ des zuerst umschlossenen Werts.  
  
 Value2  
 Der Typ des zweiten umschlossenen Werts.  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[pair::first\_type](../dotnet/pair-first-type-stl-clr.md)|Der Typ des zuerst umschlossenen Werts.|  
|[pair::second\_type](../dotnet/pair-second-type-stl-clr.md)|Der Typ des zweiten umschlossenen Werts.|  
  
|Member\-Objekt|**Beschreibung**|  
|--------------------|----------------------|  
|[pair::first](../dotnet/pair-first-stl-clr.md)|Der zuvor gespeicherte Wert.|  
|[pair::second](../dotnet/pair-second-stl-clr.md)|Der zweite gespeicherte Wert.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[pair::pair](../dotnet/pair-pair-stl-clr.md)|Erstellt ein Paarobjekt.|  
|[pair::swap](../dotnet/pair-swap-stl-clr.md)|Vertauscht den Inhalt von beiden aus Paaren.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[pair::operator\=](../dotnet/pair-operator-assign-stl-clr.md)|Ersetzt die gespeicherten Paare von Werten.|  
  
## Hinweise  
 Das Objekt speichert ein Paar Werte.  Sie verwenden diese Vorlagenklasse, um zwei Werte in einem einzelnes Objekt zu vereinen.  Beachten Sie, dass `cliext::pair` \(hier beschrieben\) nur verwaltete Typen speichert; um ein Paar nicht verwaltete Typen speichern verwenden Sie `std::pair`, deklariert in `<utility>`.  
  
## Anforderungen  
 **Header:** \<cliext\/Hilfsprogramm\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [make\_pair](../dotnet/make-pair-stl-clr.md)