---
title: "function-Klasse"
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
  - "functional/std::tr1::function"
  - "std.tr1.function"
  - "std::tr1::function"
  - "function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "function-Klasse [TR1]"
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# function-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wrapper für ein aufrufbares Objekt.  
  
## Syntax  
  
```cpp  
template<class Fty>  
   class function  // Fty of type Ret(T1, T2, ..., TN)  
   : public unary_function<T1, Ret>       // when Fty is Ret(T1)  
   : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)  
   {  
public:  
   typedef Ret result_type;  
  
   function();  
   function(nullptr_t);  
   function(const function& _Right);  
   template<class Fty2>  
      function(Fty2 fn);  
   template<class Fty2, class Alloc>  
       function (reference_wrapper<Fty2>, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       void assign (Fty2, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       assign (reference_wrapper<Fty2>, const Alloc& _Ax);  
```  
  
```cpp  
function& operator=(nullptr_t);  
function& operator=(const function&);  
template<class Fty2>  
   function& operator=(Fty2);  
template<class Fty2>  
   function& operator=(reference_wrapper<Fty2>);  
void swap(function&);  
  
explicit operator bool() const;  
result_type operator()(T1, T2, ....., TN) const;  
  
const std::type_info& target_type() const;  
template<class Fty2>  
   Fty2 *target();  
template<class Fty2>  
   const Fty2 *target() const;  
```  
  
```cpp  
   template<class Fty2>  
      void operator==(const Fty2&) const = delete;  
   template<class Fty2>  
      void operator!=(const Fty2&) const = delete;  
};  
```  
  
#### Parameter  
 `Fty`  
 Der Funktionstyp einzubindende.  
  
 `_Ax`  
 Die Zuweisungsfunktion.  
  
## Hinweise  
 Die Vorlagenklasse ist ein Aufrufswrapper, dessen Aufrufsunterzeichnung `Ret(T1, T2, ..., TN)` ist.  Sie verwenden sie, um verschiedenste aufrufbaren Objekten in einem einheitlichen Wrapper einzuschließen.  
  
 Einige Memberfunktionen akzeptieren einen Operanden, der das gewünschte Zielobjekt benennt.  Sie können ein solches Operanden auf mehrere Arten angegeben werden:  
  
 `fn` \- das aufrufbare Objekt `fn`; nachdem der Aufruf das `function`\-Objekt eine Kopie von `fn` enthält  
  
 `fnref` \- das aufrufbare Objekt mit dem Namen von `fnref.get()`; nachdem der Aufruf das `function`\-Objekt einen Verweis auf `fnref.get()` enthält  
  
 `right` \- das aufrufbare Objekt ggf. angehalten vom `function`\-Objekt `right`  
  
 `npc` \- ein NULL\-Zeiger; nach dem Aufruf ist das `function`\-Objekt leer  
  
 In allen Fällen muss `INVOKE(f, t1, t2, ..., tN)`, wobei `f` das aufrufbare Objekt ist und `t1, t2, ..., tN` lvalues der Typen `T1, T2, ..., TN` bzw. sind, wohl geformt und, wenn `Ret` nicht NULL ist, zu `Ret` konvertierbar sein.  
  
 Ein leeres `function`\-Objekt behält kein aufrufbares Objekt oder einen Verweis auf ein aufrufbaren Objekt.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[function::function](../Topic/function::function.md)|Erstellt einen Wrapper, dass entweder leer ist oder speichert ein aufrufbares Objekt eines beliebigen Typs mit einer festen Signatur.|  
  
### Typedefs  
  
|||  
|-|-|  
|[function::result\_type](../Topic/function::result_type.md)|Der Rückgabetyp aufrufbaren des gespeicherten Objekts.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[function::assign](../Topic/function::assign.md)|Weist ein aufrufbares Objekt zu diesem Funktionsobjekt an.|  
|[function::swap](../Topic/function::swap.md)|Aufrufbare Objekte des Austauschs zwei.|  
|[function::target](../Topic/function::target.md)|Testet, ob aufrufbares gespeichertes Objekt aufgerufen werden kann, wie angegeben.|  
|[function::target\_type](../Topic/function::target_type.md)|Ruft Typinformationen zum aufrufbare Objekt ab.|  
  
### Operatoren  
  
|||  
|-|-|  
|[function::operator nicht definiert](../Topic/function::operator%20unspecified.md)|Testet, ob aufrufbares gespeichertes Objekt vorhanden ist.|  
|[function::operator\(\)](../Topic/function::operator\(\).md)|Ruft ein aufrufbares Objekt auf.|  
|[function::operator\=](../Topic/function::operator=.md)|Ersetzt das gespeicherte aufrufbare Objekt.|  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [mem\_fn\-Funktion](../Topic/mem_fn%20Function.md)   
 [reference\_wrapper\-Klasse](../standard-library/reference-wrapper-class.md)