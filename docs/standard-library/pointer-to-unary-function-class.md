---
title: "pointer_to_unary_function-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::pointer_to_unary_function"
  - "pointer_to_unary_function"
  - "std.pointer_to_unary_function"
  - "std::pointer_to_unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_unary_function-Klasse"
  - "pointer_to_unary_function-Funktion"
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# pointer_to_unary_function-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen unären Funktionszeiger in eine anwendbare unäre Funktion.  
  
## Syntax  
  
```  
template<class Arg, class Result>  
class pointer_to_unary_function  
    : public unary_function<Arg, Result>   
    {  
    public:  
        explicit pointer_to_unary_function(  
            Result (*_pfunc)(Arg)  
        );  
        Result operator()(  
            Arg _Left  
        ) const;  
    };  
```  
  
#### Parameter  
 `_pfunc`  
 Die binäre zu konvertierende Funktion.  
  
 `_Left`  
 Das Objekt, auf das *\*\_pfunc* aufgerufen wird.  
  
## Rückgabewert  
 Die Vorlagenklasse speichert eine Kopie von **\_pfunc**.  Es definiert die Memberfunktion `operator()` als Rückgabe \(\*\)**\_pfunc**\(\_Left\).  
  
## Hinweise  
 Ein unärer Funktionszeiger ist ein Funktionsobjekt und zu jedem Standardvorlagenbibliotheksalgorithmus übergeben, der eine unäre Funktion als Parameter erwartet, jedoch wird nicht angewendet.  Um es mit einem Adapter, wie Binden eines Werts hinzufügen oder Verwendung mit einem Negator zu verwenden, muss mit geschachtelten Typen **argument\_type** und **result\_type** angegeben wurden die eine solche Anpassung ist.  Die Konvertierung von `pointer_to_unary_function`\-Funktionsadapter Arbeitsvorgänge mit binären Funktionszeiger.  
  
## Beispiel  
 Der Konstruktor des `pointer_to_unary_function` wird selten direkt verwendet.  Siehe die Hilfsfunktion [ptr\_fun](../Topic/ptr_fun%20Function.md) finden Sie ein Beispiel dafür, wie das `pointer_to_unary_function` Adapterprädikat deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)