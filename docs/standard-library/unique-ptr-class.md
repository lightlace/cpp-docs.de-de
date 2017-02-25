---
title: "unique_ptr-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unique_ptr"
  - "std.unique_ptr"
  - "std::unique_ptr"
  - "memory/std::unique_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique_ptr-Klasse"
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# unique_ptr-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es wird ein Zeiger auf ein im Besitz befindliches Objekt oder Array gespeichert.  Das Objekt\/Array ist nicht im Besitz eines anderen `unique_ptr`\-Elements.  Das Objekt\/Array wird zerstört, wenn `unique_ptr` zerstört wird.  
  
## Syntax  
  
```  
template< class T, class Del = default_delete<T> >  
    class unique_ptr {  
public:  
    unique_ptr( );  
    unique_ptr( nullptr_t Nptr );  
    explicit unique_ptr( pointer Ptr );  
    unique_ptr( pointer Ptr,  
        typename conditional<is_reference<Del>::value,   
            Del,  
            typename add_reference<const Del>::type>::type Deleter);  
    unique_ptr (pointer Ptr,  
        typename remove_reference<Del>::type&& Deleter);  
    unique_ptr (unique_ptr&& Right);  
    template<class T2, Class Del2> unique_ptr( unique_ptr<T2, Del2>&& Right );  
    unique_ptr( const unique_ptr& Right    ) = delete;  
    unique_ptr& operator=(const unique_ptr& Right     ) = delete;  
};  
  
```  
  
```  
//Specialization for arrays:  
template <class T, class D> class unique_ptr<T[], D>   
{   public:       
     typedef pointer;  
     typedef T element_type;  
     typedef D deleter_type;  
  
     constexpr unique_ptr() noexcept;  
     template <class U> explicit unique_ptr(U p) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     unique_ptr(unique_ptr&& u) noexcept;  
     constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }  
     template <class U, class E>  
       unique_ptr(unique_ptr<U, E>&& u) noexcept;  
  
     ~unique_ptr();  
  
     unique_ptr& operator=(unique_ptr&& u) noexcept;  
     template <class U, class E>  
       unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;  
     unique_ptr& operator=(nullptr_t) noexcept;  
  
     T& operator[](size_t i) const;  
     pointer get() const noexcept;  
     deleter_type& get_deleter() noexcept;  
     const deleter_type& get_deleter() const noexcept;  
     explicit operator bool() const noexcept;  
  
     pointer release() noexcept;  
     void reset(pointer p = pointer()) noexcept;  
     void reset(nullptr_t = nullptr) noexcept;  
     template <class U> void reset(U p) noexcept = delete;  
     void swap(unique_ptr& u) noexcept;  
  
    // disable copy from lvalue  
     unique_ptr(const unique_ptr&) = delete;  
     unique_ptr& operator=(const unique_ptr&) = delete;  
   };  
 }  
  
```  
  
#### Parameter  
 `Right`  
 Ein `unique_ptr`.  
  
 `Nptr`  
 Ein `rvalue` vom Typ `std::nullptr_t`.  
  
 `Ptr`  
 Ein `pointer`.  
  
 `Deleter`  
 Eine `deleter`\-Funktion, die an `unique_ptr` gebunden ist.  
  
## Ausnahmen  
 Es werden keine Ausnahmen von `unique_ptr` generiert.  
  
## Hinweise  
 Die `unique_ptr`\-Klasse löst `auto_ptr` ab und kann als Element in STL\-Containern verwendet werden.  
  
 Verwenden Sie die [make\_unique](../Topic/make_unique.md)\-Hilfsfunktion, um neue Instanzen von `unique_ptr` effizient zu erstellen.  
  
 `unique_ptr` verwaltet eine Ressource eindeutig.  Jedes `unique_ptr`\-Objekt speichert einen Zeiger auf das Objekt, das es besitzt, oder speichert einen NULL\-Zeiger.  Eine Ressource kann sich nur im Besitz eines `unique_ptr`\-Objekts befinden.  Wenn ein `unique_ptr`\-Objekt zerstört wird, in dessen Besitz sich eine bestimmte Ressource befindet, wird die Ressource freigegeben.  Ein `unique_ptr`\-Objekt kann verschoben, aber nicht kopiert werden.  Weitere Informationen finden Sie unter [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Die Ressource wird freigegeben, indem ein gespeichertes `deleter`\-Objekt vom Typ `Del` aufgerufen wird, dem bekannt ist, wie Ressourcen für ein bestimmtes `unique_ptr`\-Objekt zugeordnet werden.  Der standardmäßige `deleter` `default_delete``<T>` geht davon aus, dass die Ressource, auf die `_Ptr` zeigt, `new` zugeordnet wird und dass sie freigegeben werden kann, indem `delete _``Ptr` aufgerufen wird.  \(Eine partielle `unique_ptr<T[]>`\-Spezialisierung verwaltet Arrayobjekte, die `new[]` zugeordnet sind, und verfügt über den Standardwert `deleter` `default_delete<T[]>`, der auf den Aufruf von delete\[\] `_Ptr` spezialisiert ist.\)  
  
 Der gespeicherte Zeiger auf eine zugehörige Ressource `stored_ptr` ist vom Typ `pointer`.  Er lautet `Del::pointer`, wenn er definiert ist, und `T *` , wenn er nicht definiert ist.  Das gespeicherte `deleter`\-Objekt `stored_deleter` belegt keinen Speicherplatz im Objekt, wenn `deleter` zustandslos ist.  Beachten Sie, dass `Del` ein Verweistyp sein kann.  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[unique\_ptr::unique\_ptr](../Topic/unique_ptr::unique_ptr.md)|Es gibt sieben Konstruktoren für `unique_ptr`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[deleter\_type](../Topic/deleter_type.md)|Ein Synonym für den Vorlagenparameter `Del`.|  
|[element\_type](../Topic/element_type.md)|Ein Synonym für den Vorlagenparameter `T``.`|  
|[Zeiger](../Topic/pointer.md)|Ein Synonym für `Del::pointer`, wenn der Wert definiert ist; andernfalls `T *`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[unique\_ptr::get](../Topic/unique_ptr::get.md)|Gibt `stored_ptr`zurück.|  
|[unique\_ptr::get\_deleter](../Topic/unique_ptr::get_deleter.md)|Gibt einen Verweis auf `stored_deleter` zurück.|  
|[unique\_ptr::release](../Topic/unique_ptr::release.md)|speichert `pointer()` in `stored_ptr` und gibt seinen vorherigen Inhalt zurück.|  
|[unique\_ptr::reset](../Topic/unique_ptr::reset.md)|Gibt die zurzeit zugehörige Ressource frei und akzeptiert eine neue Ressource.|  
|[unique\_ptr::swap](../Topic/unique_ptr::swap.md)|Tauscht die Ressource und `deleter` mit dem bereitgestellten `unique_ptr`\-Objekt aus.|  
  
### Operatoren  
  
|||  
|-|-|  
|`operator bool`|Der Operator gibt einen Wert eines Typs zurück, der in `bool` konvertiert werden kann.  Das Ergebnis der Konvertierung in `bool` ist `true`, wenn `get() != pointer()`, andernfalls `false`.|  
|`operator->`|Die Memberfunktion gibt `stored_ptr``.` zurück.|  
|`operator*`|Die Memberfunktion gibt \*`stored_ptr``.` zurück.|  
|[unique\_ptr operator\=](../Topic/unique_ptr%20operator=.md)|Weist den Wert eines `unique_ptr` \-Objekts \(oder eines `pointer-type`\) dem aktuellen `unique_ptr`\-Objekt zu.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<memory\>](../standard-library/memory.md)