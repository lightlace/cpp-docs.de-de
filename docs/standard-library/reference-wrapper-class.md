---
title: "reference_wrapper-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.reference_wrapper"
  - "tr1.reference_wrapper"
  - "reference_wrapper"
  - "tr1::reference_wrapper"
  - "xrefwrap/std::tr1::reference_wrapper"
  - "std::tr1::reference_wrapper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference_wrapper-Klasse"
  - "reference_wrapper-Klasse [TR1]"
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# reference_wrapper-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt einen Verweis.  
  
## Syntax  
  
```  
template<class Ty>  
    class reference_wrapper  
    : public unary_function<T1, Ret>        // see below  
    : public binary_function<T1, T2, Ret>   // see below  
    {  
public:  
    typedef Ty type;  
    typedef T0 result_type;                 // see below  
  
    reference_wrapper(Ty&);  
  
    Ty& get() const;  
    operator Ty&() const;  
    template<class T1, class T2, ..., class TN>  
        typename result_of<T(T1, T2, ..., TN)>::type  
        operator()(T1&, T2&, ..., TN&);  
  
private:  
    Ty *ptr; // exposition only  
    };  
```  
  
## Hinweise  
 Ein `reference_wrapper<Ty>`\-Objekt kann über eine Kopie erstellt und zugewiesen werden und enthält einen Zeiger, der auf ein Objekt des Typs `Ty` zeigt.  
  
 Ein `reference_wrapper<Ty>`\-Spezialisierungsobjekt wird nur dann aus `std::unary_function<T1, Ret>` abgeleitet \(somit definiert es den geschachtelten Typ `result_type` als Synonym für `Ret` und den geschachtelten Typ `argument_type` als Synonym für `T1`\), wenn für den Typ `Ty` Folgendes gilt:  
  
 Er ist ein Funktionstyp oder ein Zeiger auf einen Funktionstyp, der ein Argument des Typs `T1` hat und `Ret` zurückgibt; oder  
  
 er ist ein Zeiger auf eine Memberfunktion `Ret T::f() cv`, wobei `cv` den cv\-Qualifizierern der Memberfunktion entspricht; der Typ `T1` ist `cv` `T*`; oder  
  
 er ist ein Klassentyp, der aus `unary_function<T1, Ret>` abgeleitet wurde.  
  
 Ein `reference_wrapper<Ty>`\-Spezialisierungsobjekt wird nur dann aus `std::binary_function<T1, T2, Ret>` abgeleitet \(somit definiert es den geschachtelten Typ `result_type` als Synonym für `Ret`, den geschachtelten Typ `first_argument_type` als Synonym für `T1` und den geschachtelten Typ `second_argument_type` als Synonym für `T2`\), wenn für den Typ `Ty` Folgendes gilt:  
  
 Er ist ein Funktionstyp oder ein Zeiger auf einen Funktionstyp, der zwei Argumente des Typs `T1` und `T2` hat und `Ret` zurückgibt; oder  
  
 er ist ein Zeiger auf eine Memberfunktion `Ret T::f(T2) cv`, wobei `cv` den cv\-Qualifizierern der Memberfunktion entspricht; der Typ `T1` ist `cv` `T*`; oder  
  
 er ist ein Klassentyp, der aus `binary_function<T1, T2, Ret>` abgeleitet wurde.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[reference\_wrapper::reference\_wrapper](../Topic/reference_wrapper::reference_wrapper.md)|Erstellt ein Objekt vom Typ `reference_wrapper`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[reference\_wrapper::result\_type](../Topic/reference_wrapper::result_type.md)|Der schwache Ergebnistyp des umschlossenen Verweises.|  
|[reference\_wrapper::type](../Topic/reference_wrapper::type.md)|Der Typ des umschlossenen Verweises.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[reference\_wrapper::get](../Topic/reference_wrapper::get.md)|Ruft den umschlossenen Verweis ab.|  
  
### Operatoren  
  
|||  
|-|-|  
|[reference\_wrapper::operator Ty&](../Topic/reference_wrapper::operator%20Ty&.md)|Ruft einen Zeiger auf den umschlossenen Verweis ab.|  
|[reference\_wrapper::operator\(\)](../Topic/reference_wrapper::operator\(\).md)|Ruft den umschlossenen Verweis auf.|  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [cref\-Funktion](../Topic/cref%20Function.md)   
 [ref\-Funktion](../Topic/ref%20Function.md)