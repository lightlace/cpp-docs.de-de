---
title: "pointer_to_binary_function-Klasse"
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
  - "std::pointer_to_binary_function"
  - "xfunctional/std::pointer_to_binary_function"
  - "pointer_to_binary_function"
  - "std.pointer_to_binary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_binary_function-Klasse"
  - "pointer_to_binary_function-Funktion"
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# pointer_to_binary_function-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion.  
  
## Syntax  
  
```  
template<class Arg1, class Arg2, class Result>  
   class pointer_to_binary_function   
   : public binary_function <Arg1, Arg2, Result>   
   {  
   public:  
   explicit pointer_to_binary_function(  
      Result (*_pfunc )( Arg1, Arg2 )   
   );  
   Result operator()(  
      Arg1 _Left,   
      Arg2 _Right  
   ) const;  
   };  
```  
  
#### Parameter  
 `_pfunc`  
 Die binäre zu konvertierende Funktion.  
  
 `_Left`  
 Das linksobjekt, dass um den *\*\_pfunc* aufgerufen wird.  
  
 `_Right`  
 Das richtige Objekt, dass das *\*\_pfunc* aufgerufen wird.  
  
## Rückgabewert  
 Die Vorlagenklasse speichert eine Kopie von **\_pfunc**.  Es definiert die Memberfunktion `operator()` als Rückgabe \(\*\)**\_pfunc**\(\_Left, \_Right\).  
  
## Hinweise  
 Ein binärer Funktionszeiger ist ein Funktionsobjekt und zu jedem Standardvorlagenbibliotheksalgorithmus übergeben, der eine binäre Funktion als Parameter erwartet, jedoch wird nicht angewendet.  Um es mit einem Adapter, wie Binden eines Werts hinzufügen oder Verwendung mit einem Negator zu verwenden, muss mit geschachtelten Typen **first\_argument\_type**, **second\_argument\_type** und **result\_type** angegeben wurden die eine solche Anpassung ist.  Die Konvertierung von `pointer_to_binary_function`\-Funktionsadapter Arbeitsvorgänge mit binären Funktionszeiger.  
  
## Beispiel  
 Der Konstruktor des `pointer_to_binary_function` wird selten direkt verwendet.  Siehe die Hilfsfunktion [ptr\_fun](../Topic/ptr_fun%20Function.md) finden Sie ein Beispiel dafür, wie das `pointer_to_binary_function` Adapterprädikat deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)