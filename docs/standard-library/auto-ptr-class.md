---
title: "auto_ptr-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::auto_ptr"
  - "std.auto_ptr"
  - "auto_ptr"
  - "memory/std::auto_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_ptr-Klasse"
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# auto_ptr-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt eine Ressource in einen intelligenten Zeiger ein, der sicherstellt, dass die Ressource automatisch zerstört wird, wenn die Steuerung einen Block verlässt.  
  
 Die leistungsfähigere `unique_ptr`\-Klasse ersetzt `auto_ptr`.  Weitere Informationen finden Sie unter [unique\_ptr\-Klasse](../standard-library/unique-ptr-class.md).  
  
 Weitere Informationen zu `throw()` und zur Behandlung von Ausnahmen finden Sie unter [Ausnahmespezifikationen \(throw\)](../cpp/exception-specifications-throw-cpp.md).  
  
## Syntax  
  
```  
template<class Type>  
    class auto_ptr {  
public:  
    typedef Type element_type;  
    explicit auto_ptr(Type *_Ptr = 0) throw();  
    auto_ptr(auto_ptr<Type>& _Right) throw();  
    template<class Other>  
        operator auto_ptr<Other>() throw();  
    template<class Other>  
        auto_ptr<Type>& operator=(auto_ptr<Other>& _Right) throw();  
    template<class Other>  
        auto_ptr(auto_ptr<Other>& _Right);  
    auto_ptr<Type>& operator=(auto_ptr<Type>& _Right);  
    ~auto_ptr();  
    Type& operator*() const throw();  
    Type *operator->()const throw();  
    Type *get() const throw();  
    Type *release()throw();  
    void reset(Type *_Ptr = 0);  
};  
```  
  
#### Parameter  
 `_Right`  
 Der `auto_ptr`, aus dem eine vorhandene Ressource abgerufen werden soll.  
  
 `_Ptr`  
 Der Zeiger, der den gespeicherten Zeiger ersetzen soll.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt einen intelligenten Zeiger, der als ein `auto_ptr,` bezeichnet wird, auf ein zugeordnetes Objekt.  Der Zeiger muss entweder gleich NULL oder ein Objekt sein, das durch `new` zugeordnet ist.  Der `auto_ptr` übergibt den Besitz, wenn sein gespeicherter Wert einem anderen Objekt zugewiesen wird.  \(Er ersetzt den gespeicherten Wert nach einer Übergabe mit einem NULL\-Zeiger.\) Der Destruktor für `auto_ptr<Type>` löscht das zugeordnete Objekt.  Der `auto_ptr<Type>` stellt sicher, dass ein zugeordnetes Objekt automatisch gelöscht wird, wenn die Steuerung einen Block verlässt, selbst wenn dies über eine ausgelöste Ausnahme erfolgt.  Sie sollten nicht zwei `auto_ptr<Type>`\-Objekte erstellen, die Eigentümer desselben Objekts sind.  
  
 Sie können ein `auto_ptr<Type>`\-Objekt als Wert als ein Argument für einen Funktionsaufruf übergeben.  Ein `auto_ptr`\-Objekt kann kein Element eines Standardbibliothekcontainers sein.  Es ist nicht möglich, eine Sequenz von `auto_ptr<Type>`\-Objekten zuverlässig mit einem Container für eine Standardvorlagenbibliothek zu verwalten.  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[auto\_ptr](../Topic/auto_ptr::auto_ptr.md)|Der Konstruktor für Objekte des Typs `auto_ptr`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[element\_type](../Topic/auto_ptr::element_type.md)|Der Type stellt ein Synonym für den Vorlagenparameter `Type` dar.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Abrufen](../Topic/auto_ptr::get.md)|Die Memberfunktion gibt den gespeicherten Zeiger `myptr` zurück.|  
|[Freigabe](../Topic/auto_ptr::release.md)|Der Member ersetzt den gespeicherten Zeiger `myptr` durch einen NULL\-Zeiger und gibt den zuvor gespeicherten Zeiger zurück.|  
|[zurücksetzen](../Topic/auto_ptr::reset.md)|Die Memberfunktion wertet den Ausdruck `delete myptr` aus, allerdings nur, wenn sich der Wert des gespeicherten Zeigers `myptr` aufgrund eines Funktionsaufrufs ändert.  Anschließend ersetzt die Funktion den gespeicherten Zeiger durch `ptr`.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/auto_ptr::operator=.md)|Ein Zuweisungsoperator, der den Besitz von einem `auto_ptr`\-Objekt an ein anderes Objekt übergibt.|  
|[operator\*](../Topic/auto_ptr::operator*.md)|Der dereferenzierende Operator für Objekte des Typs `auto_ptr`.|  
|[operator\-\>](../Topic/auto_ptr::operator-%3E.md)|Der Operator zum Ermöglichen von Memberzugriff.|  
|[operator auto\_ptr\<Other\>](../Topic/auto_ptr::operator%20auto_ptr%3COther%3E.md)|Nimmt eine Umwandlung aus einer Art von `auto_ptr` in eine andere Art von `auto_ptr` vor.|  
|[operator auto\_ptr\_ref\<Other\>](../Topic/auto_ptr::operator%20auto_ptr_ref%3COther%3E.md)|Nimmt eine Umwandlung von einem `auto_ptr` zu einem anderen `auto_ptr_ref` vor.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique\_ptr\-Klasse](../standard-library/unique-ptr-class.md)