---
title: "weak_ptr-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.weak_ptr"
  - "tr1.weak_ptr"
  - "weak_ptr"
  - "tr1::weak_ptr"
  - "std::tr1::weak_ptr"
  - "memory/std::tr1::weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "weak_ptr-Klasse"
  - "weak_ptr-Klasse [TR1]"
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# weak_ptr-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt einen schwach verknüpften Zeiger.  
  
## Syntax  
  
```  
template<class Ty> class weak_ptr {  
public:  
    typedef Ty element_type;  
  
    weak_ptr();  
    weak_ptr(const weak_ptr&);  
    template<class Other>  
        weak_ptr(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr(const shared_ptr<Other>&);  
  
    weak_ptr& operator=(const weak_ptr&);  
    template<class Other>  
        weak_ptr& operator=(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr& operator=(shared_ptr<Other>&);  
  
    void swap(weak_ptr&);  
    void reset();  
  
    long use_count() const;  
    bool expired() const;  
    shared_ptr<Ty> lock() const;  
    };  
```  
  
#### Parameter  
 `Ty`  
 Der vom schwachen Zeiger gesteuerte Typ.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das auf eine Ressource verweist, die von mindestens einem [shared\_ptr\-Klasse](../standard-library/shared-ptr-class.md)\-Objekt verwaltet wird.  Die `weak_ptr`\-Objekte, die auf eine Ressource verweisen, wirken sich nicht auf den Verweiszähler der Ressource aus.  Daher wird die Ressource, wenn das letzte `shared_ptr`\-Objekt, das diese Ressource verwaltet, zerstört wurde, selbst dann freigegeben, wenn es `weak_ptr`\-Objekte gibt, die auf diese Ressource verweisen.  Dies ist entscheidend für die Vermeidung von Zyklen in Datenstrukturen.  
  
 Ein `weak_ptr`\-Objekt verweist auf eine Ressource, wenn es aus einem `shared_ptr`\-Objekt erstellt wurde, das diese Ressource besitzt, wenn es aus einem `weak_ptr`\-Objekt erstellt wurde, das auf diese Ressource verweist, oder wenn ihm diese Ressource mit [weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md) zugewiesen wurde.  Ein `weak_ptr`\-Objekt stellt keinen direkten Zugriff auf die Ressource bereit, auf die es verweist.  Code, der auf die Ressource zugreifen muss, erledigt dies über ein `shared_ptr`\-Objekt, das diese Ressource besitzt, die durch Aufrufen der Memberfunktion [weak\_ptr::lock](../Topic/weak_ptr::lock.md) erstellt wurde.  Ein `weak_ptr`\-Objekt ist abgelaufen, wenn die Ressource, auf die es verweist, freigegeben wurde, weil alle `shared_ptr`\-Objekte zerstört wurden, die die Ressource besitzen.  Ein Aufrufen von `lock` für ein `weak_ptr`\-Objekt, das abgelaufen ist, erstellt ein leeres shared\_ptr\-Objekt.  
  
 Ein leeres weak\_ptr\-Objekt verweist auf keine Ressource und hat keinen Kontrollblock.  Ihre Memberfunktion `lock` gibt ein leeres shared\_ptr\-Objekt zurück.  
  
 Ein Zyklus tritt auf, wenn es für zwei oder mehr Ressourcen, die von `shared_ptr`\-Objekten gesteuert werden, `shared_ptr`\-Objekte gibt, die gegenseitig auf sich verweisen.  Angenommen, eine kreisförmig verknüpfte Liste mit drei Elementen hat den Kopfknoten `N0`; dieser Knoten enthält ein `shared_ptr`\-Objekt, das den nächsten Knoten, `N1`, besitzt; dieser Knoten enthält ein `shared_ptr`\-Objekt, das den nächsten Knoten, `N2`, besitzt; dieser Knoten wiederum enthält ein `shared_ptr`\-Objekt, das den Kopfknoten `N0` besitzt, wodurch der Zyklus geschlossen wird.  In diesem Fall wird keiner der Verweiszähler je den Wert 0 \(null\) annehmen, und die Knoten im Zyklus werden nicht freigegeben.  Um den Zyklus zu vermeiden, sollte der letzte Knoten, `N2`, anstelle eines `shared_ptr`\-Objekts ein `weak_ptr`\-Objekt enthalten, das auf `N0` verweist.  Da das `weak_ptr`\-Objekt kein Besitzer von `N0` ist, hat es keinen Einfluss auf den Verweiszähler von `N0`, und wenn im Programm der letzte Verweis auf den Kopfknoten zerstört wurde, werden auch die Knoten in der Liste zerstört.  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[weak\_ptr::weak\_ptr](../Topic/weak_ptr::weak_ptr.md)|Erstellt ein Objekt vom Typ `weak_ptr`.|  
  
### Methoden  
  
|||  
|-|-|  
|[weak\_ptr::element\_type](../Topic/weak_ptr::element_type.md)|Der Typ des Elements.|  
|[weak\_ptr::expired](../Topic/weak_ptr::expired.md)|Überprüft, ob der Besitz abgelaufen ist.|  
|[weak\_ptr::lock](../Topic/weak_ptr::lock.md)|Bedingt exklusiven Besitz einer Ressource.|  
|[weak\_ptr::owner\_before](../Topic/weak_ptr::owner_before.md)|Gibt `true` zurück, wenn dieses `weak_ptr`\-Objekt vor dem bereitgestellten Zeiger angeordnet \(oder kleiner als dieser\) ist.|  
|[weak\_ptr::reset](../Topic/weak_ptr::reset.md)|Gibt eine in Besitz befindliche Ressource frei.|  
|[weak\_ptr::swap](../Topic/weak_ptr::swap.md)|Tauscht zwei `weak_ptr`\-Objekte.|  
|[weak\_ptr::use\_count](../Topic/weak_ptr::use_count.md)|Ermittelt die Anzahl von festgelegten `shared_ptr`\-Objekten.|  
  
### Operatoren  
  
|||  
|-|-|  
|[weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md)|Ersetzt eine in Besitz befindliche Ressource.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [shared\_ptr\-Klasse](../standard-library/shared-ptr-class.md)