---
title: "Klassen value_compare-Klasse"
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
  - "std::value_compare"
  - "std.value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare-Klasse"
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Klassen value_compare-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Funktionsobjekt bereit, das die Elemente eines hash\_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen, um ihre relative Position im hash\_map zu bestimmen.  
  
## Syntax  
  
```  
class value_compare  
    : std::public binary_function<value_type, value_type, bool>   
{  
public:  
    bool operator( )(  
        const value_type& _Left,  
        const value_type& _Right ) const  
        {  
            return ( comp( _Left.first, _Right.first ) );   
        }  
protected:  
    value_compare( const key_compare& c ) : comp (c) { }  
    key_compare comp;  
};  
```  
  
## Hinweise  
 Die Vergleichskriterien, die vom value\_compare zwischen **value\_types** aus ganzen Elementen enthalten werden durch ein hash\_map bereitgestellt werden, wird ein Vergleich zwischen den Schlüsseln der jeweiligen Elemente durch die Erweiterungsklassenkonstruktion verursacht.  Der Memberfunktionsoperator verwendet das Objekt **Komp.** vom Typ `key_compare` gespeichert im Funktionsobjekt, das vom value\_compare bereitgestellt wird, um die Sortierschlüsselkomponenten von zwei Elementen zu vergleichen.  
  
 Für hash\_sets und hash\_multisets die einfache Container sind, in die die Schlüsselwerte zu Elementwerten identisch sind, ist value\_compare entspricht `key_compare`; für hash\_maps und hash\_multimaps sind sie nicht, da der Wert der `pair`\-Typ keine Elemente auf den Wert des Schlüssels des Elements identisch ist.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben.  Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
## Beispiel  
 Im Beispiel für [hash\_map::value\_comp](../Topic/hash_map::value_comp.md) als Beispiel dafür, wie value\_compare deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<hash\_map\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [binary\_function\-Struktur](../standard-library/binary-function-struct.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)