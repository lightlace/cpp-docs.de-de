---
title: "shared_ptr-Klasse"
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
  - "shared_ptr"
  - "tr1::shared_ptr"
  - "memory/std::tr1::shared_ptr"
  - "std::tr1::shared_ptr"
  - "std.tr1.shared_ptr"
  - "tr1.shared_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared_ptr-Klasse"
  - "shared_ptr-Klasse [TR1]"
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
caps.latest.revision: 29
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# shared_ptr-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt einen intelligenten Zeiger mit Verweiszählung um ein dynamisch zugeordnetes Objekt.  
  
## Syntax  
  
```  
template<class Ty>  
   class shared_ptr {  
public:  
    typedef Ty element_type;  
  
    shared_ptr();  
    shared_ptr(nullptr_t);   
    shared_ptr(const shared_ptr& sp);  
    shared_ptr(shared_ptr&& sp);  
    template<class Other>  
        explicit shared_ptr(Other * ptr);  
    template<class Other, class D>  
        shared_ptr(Other * ptr, D dtor);  
    template<class D>  
        shared_ptr(nullptr_t, D dtor);  
    template<class Other, class D, class A>  
        shared_ptr(Other *ptr, D dtor, A alloc);  
    template<class D, class A>  
        shared_ptr(nullptr_t, D dtor, A alloc);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>&& sp);  
    template<class Other>  
        explicit shared_ptr(const weak_ptr<Other>& wp);  
    template<class Other>  
        shared_ptr(auto_ptr<Other>& ap);  
    template<class Other, class D>  
        shared_ptr(unique_ptr<Other, D>&& up);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp, Ty *ptr);  
    ~shared_ptr();  
    shared_ptr& operator=(const shared_ptr& sp);  
    template<class Other>   
        shared_ptr& operator=(const shared_ptr<Other>& sp);  
    shared_ptr& operator=(shared_ptr&& sp);  
    template<class Other>   
        shared_ptr& operator=(shared_ptr<Other>&& sp);  
    template<class Other>   
        shared_ptr& operator=(auto_ptr< Other >&& ap);  
    template <class Other, class D>   
        shared_ptr& operator=(const unique_ptr< Other, D>& up) = delete;  
    template <class Other, class D>  
        shared_ptr& operator=(unique_ptr<Other, D>&& up);  
    void swap(shared_ptr& sp);  
    void reset();  
    template<class Other>  
        void reset(Other *ptr);  
    template<class Other, class D>  
        void reset(Other *ptr, D dtor);  
    template<class Other, class D, class A>  
        void reset(Other *ptr, D dtor, A alloc);  
    Ty *get() const;  
    Ty& operator*() const;  
    Ty *operator->() const;  
    long use_count() const;  
    bool unique() const;  
    operator bool() const;  
  
    template<class Other>  
        bool owner_before(shared_ptr<Other> const& ptr) const;  
    template<class Other>  
        bool owner_before(weak_ptr<Other> const& ptr) const;  
    template<class D, class Ty>   
        D* get_deleter(shared_ptr<Ty> const& ptr);  
};  
  
```  
  
#### Parameter  
 `Ty`  
 Der vom freigegebenen Zeiger gesteuerte Typ.  
  
 `Other`  
 Der vom Argumentzeiger gesteuerte Typ.  
  
 `ptr`  
 Der zu kopierende Zeiger.  
  
 `D`  
 Der Deleter\-Typ.  
  
 `A`  
 Der Zuweisungstyp.  
  
 `dtor`  
 Der Deleter.  
  
 `alloc`  
 Die Zuweisung.  
  
 `sp`  
 Der zu kopierende oder zu verschiebende intelligente Zeiger.  
  
 `wp`  
 Der zu kopierende oder zu verschiebende schwache Zeiger.  
  
 `ap`  
 Der zu kopierende oder zu verschiebende automatische Zeiger.  
  
 `up`  
 Der zu verschiebende eindeutige Zeiger.  
  
## Hinweise  
 Mit der Vorlagenklasse wird ein Objekt beschrieben, das Ressourcen durch das Zählen von Verweisen verwaltet.  Ein Objekt vom Typ `shared_ptr` enthält einen Zeiger auf die Ressource, die es besitzt, oder es enthält einen NULL\-Zeiger.  Es können mehrere `shared_ptr`\-Objekte eine Ressource besitzen. Wird das letzte `shared_ptr`\-Objekt beschädigt, das eine bestimmte Ressource besitzt, wird die Ressource freigegeben.  
  
 Ein `shared_ptr` ist nicht mehr Besitzer einer Ressource, wenn diese zurückgesetzt oder neu zugewiesen wird.  
  
 Das Vorlagenargument `Ty` kann ein unvollständiger Typ sein, außer wie für bestimmte Memberfunktionen aufgeführt.  
  
 Wenn ein `shared_ptr<Ty>`\-Objekt von einem Ressourcenzeiger des Typs `G*` oder von einem `shared_ptr<G>` erstellt wird, muss der Zeigertyp `G*` konvertierbar sein in `Ty*`.  Wenn dies nicht der Fall ist, wird der Code nicht berechnet.  Zum Beispiel:  
  
```cpp  
class F {};  
class G : public F {};  
```  
  
```cpp  
  
#include <memory>  
  
using namespace std;  
  
shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*  
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>  
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*  
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>  
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>  
shared_ptr<int> sp5(new G); // error, G* not convertible to int*  
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>  
```  
  
 Ein `shared_ptr`\-Objekt besitzt in diesen Fällen eine Ressource:  
  
-   Es wurde mit einem Zeiger auf diese Ressource erstellt.  
  
-   Es wurde von einem `shared_ptr`\-Objekt erstellt, das diese Ressource besitzt.  
  
-   Es wurde aus einem [weak\_ptr\-Klasse](../standard-library/weak-ptr-class.md)\-Objekt erstellt, das auf diese Ressource zeigt.  
  
-   Dem Objekt wurde der Besitz dieser Ressource zugewiesen, entweder durch [shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md) oder durch Aufrufen der Memberfunktion [shared\_ptr::reset](../Topic/shared_ptr::reset.md).  
  
 Von den `shared_ptr`\-Objekten, die eine Ressource besitzen, wird ein Kontrollblock gemeinsam verwendet.  Der Kontrollblock enthält:  
  
-   Die Anzahl von `shared_ptr`\-Objekten, die die Ressource besitzen  
  
-   Die Anzahl von `weak_ptr`\-Objekten, die auf die Ressource verweisen  
  
-   Den Deleter für diese Ressource, falls vorhanden  
  
-   Die benutzerdefinierte Zuweisung für den Kontrollblock, falls vorhanden  
  
 Ein `shared_ptr`\-Objekt, das mit einem Null\-Zeiger initialisiert wird, verfügt über einen Kontrollblock und ist nicht leer.  Eine von einem `shared_ptr`\-Objekt freigegebene Ressource ist nicht mehr im Besitz dieses Objekts.  Nachdem ein `weak_ptr`\-Objekt eine Ressource freigegeben hat, verweist es nicht mehr darauf.  
  
 Wenn die Anzahl von `shared_ptr`\-Objekten, die eine Ressource besitzen, Null ergibt, wird die Ressource freigegeben. Dazu wird sie entweder gelöscht, oder ihre Adresse wird an einen Deleter übergeben. Das Verfahren hängt davon ab, wie die Besitzrechte der Ressource ursprünglich erstellt wurden.  Wenn die Anzahl von `shared_ptr`\-Objekten, die eine Ressource besitzen, null ist und auch die Anzahl von `weak_ptr`\-Objekten, die auf diese Ressource zeigen, null ist, wird der Kontrollblock freigegeben. Dazu wird die benutzerdefinierte Zuweisung für den Kontrollblock verwendet, falls vorhanden.  
  
 Ein leeres `shared_ptr`\-Objekt besitzt keine Ressourcen und verfügt über keinen Kontrollblock.  
  
 Ein Deleter ist ein Funktionsobjekt mit einer Memberfunktion `operator()`.  Für den Typ muss eine Kopie erstellt werden können. Vom Kopierkonstruktor und vom Destruktor dürfen keine Ausnahmen ausgelöst werden.  Als Parameter akzeptiert wird das zu löschende Objekt.  
  
 Von einigen Funktionen wird eine Argumentliste verwendet, mit der Eigenschaften des resultierenden `shared_ptr<Ty>`\- oder `weak_ptr<Ty>`\-Objekts definiert werden.  Sie können eine solche Argumentliste wie folgt angeben:  
  
 Keine Argumente \-\- das resultierende Objekt ist ein leeres `shared_ptr`\-Objekt oder ein leeres `weak_ptr`\-Objekt.  
  
 `ptr` \-\-ein Zeiger des Typs `Other*` auf die zu verwaltende Ressource.  `Ty` muss ein vollständiger Typ sein.  Wenn bei der Funktion Fehler auftreten \(da der Kontrollblock nicht zugeordnet werden kann\), wird der Ausdruck `delete ptr` ausgewertet.  
  
 `ptr, dtor` \-\- ein Zeiger des Typs `Other*` auf die zu verwaltende Ressource und ein Deleter für diese Ressource.  Wenn bei der Funktion Fehler auftreten \(da der Kontrollblock nicht zugeordnet werden kann\), wird `dtor(ptr)` aufgerufen \(muss klar definiert sein\).  
  
 `ptr, dtor, alloc` \-\- ein Zeiger des Typs `Other*` auf die zu verwaltende Ressource, ein Deleter für diese Ressource und eine Zuweisung zum Verwalten von Speicher, der zugeordnet und freigegeben werden muss.  Wenn bei der Funktion Fehler auftreten \(da der Kontrollblock nicht zugeordnet werden kann\), wird `dtor(ptr)` aufgerufen \(muss klar definiert sein\).  
  
 `sp` \-\- ein `shared_ptr<Other>`\-Objekt, das die zu verwaltende Ressource besitzt.  
  
 `wp` \-\- ein `weak_ptr<Other>`\-Objekt, das auf die zu verwaltende Ressource zeigt.  
  
 `ap` \-\- ein `auto_ptr<Other>`\-Objekt, das einen Zeiger auf die zu verwaltende Ressource enthält.  Wenn die Funktion erfolgreich ist, wird `ap.release()` aufgerufen. Andernfalls bleibt `ap` unverändert.  
  
 In allen Fällen muss der Zeigertyp `Other*` konvertiert werden können in `Ty*`.  
  
## Threadsicherheit  
 Mehrere Threads können verschiedene `shared_ptr`\-Objekte gleichzeitig lesen und schreiben, auch wenn die Objekte Kopien sind, die sich den Besitz teilen.  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[shared\_ptr::shared\_ptr](../Topic/shared_ptr::shared_ptr.md)|Erstellt ein Objekt vom Typ `shared_ptr`.|  
|[shared\_ptr::~shared\_ptr](../Topic/shared_ptr::~shared_ptr.md)|Beschädigt ein Objekt vom Typ `shared_ptr`.|  
  
### Methoden  
  
|||  
|-|-|  
|[shared\_ptr::element\_type](../Topic/shared_ptr::element_type.md)|Der Typ eines Elements.|  
|[shared\_ptr::get](../Topic/shared_ptr::get.md)|Ruft die Adresse der Ressource ab, die Eigentum ist.|  
|[shared\_ptr::owner\_before](../Topic/shared_ptr::owner_before.md)|Gibt True zurück, wenn dieses `shared_ptr` vor dem bereitgestellten Zeiger sortiert wird \(Operator "Before" oder "Less than"\).|  
|[shared\_ptr::reset](../Topic/shared_ptr::reset.md)|Ersetzt die Ressource, die Eigentum ist.|  
|[shared\_ptr::swap](../Topic/shared_ptr::swap.md)|Tauscht zwei `shared_ptr`\-Objekte.|  
|[shared\_ptr::unique](../Topic/shared_ptr::unique.md)|Prüft, ob die Ressource eindeutig ist, die Eigentum ist.|  
|[shared\_ptr::use\_count](../Topic/shared_ptr::use_count.md)|Zählt Ressourcenbesitzer.|  
  
### Operatoren  
  
|||  
|-|-|  
|[shared\_ptr::operator boolean\-type](../Topic/shared_ptr::operator%20boolean-type.md)|Prüft, ob eine Ressource vorhanden ist, die Eigentum ist.|  
|[shared\_ptr::operator\*](../Topic/shared_ptr::operator*.md)|Ruft den angegebenen Wert ab.|  
|[shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md)|Ersetzt die Ressource, die Eigentum ist.|  
|[shared\_ptr::operator\-\>](../Topic/shared_ptr::operator-%3E.md)|Ruft einen Zeiger auf den angegebenen Wert ab.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [weak\_ptr\-Klasse](../standard-library/weak-ptr-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)