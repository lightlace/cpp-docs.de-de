---
title: "vector (STL/CLR)"
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
  - "cliext::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/vector>-Header [STL/CLR]"
  - "<vector>-Header [STL/CLR]"
  - "Vektorklasse [STL/CLR]"
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die wahlfreien Zugriff hat.  Mit dem Container `vector`, um eine Sequenz von Elementen als zusammenhängender Block Speicher zu verwalten.  Der Block wird implementiert als Array, das bei Bedarf vergrößert.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `Value` identisch, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Value^` dar.  
  
## Syntax  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[vector::const\_reference](../dotnet/vector-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[vector::const\_reverse\_iterator](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[vector::difference\_type](../dotnet/vector-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[vector::generic\_iterator](../dotnet/vector-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[vector::generic\_reverse\_iterator](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[vector::generic\_value](../dotnet/vector-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[vector::iterator](../dotnet/vector-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[vector::reference](../dotnet/vector-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[vector::reverse\_iterator](../dotnet/vector-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[vector::size\_type](../dotnet/vector-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[vector::value\_type](../dotnet/vector-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[vector::assign](../dotnet/vector-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[vector::at](../dotnet/vector-at-stl-clr.md)|Greift auf ein Element in einer angegebenen Position zu.|  
|[vector::back](../dotnet/vector-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[vector::begin](../dotnet/vector-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[vector::capacity](../dotnet/vector-capacity-stl-clr.md)|Ermittelt die Größe des zugeordneten Speichers für den Container.|  
|[vector::clear](../dotnet/vector-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[vector::empty](../dotnet/vector-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[vector::end](../dotnet/vector-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[vector::erase](../dotnet/vector-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[vector::front](../dotnet/vector-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[vector::insert](../dotnet/vector-insert-stl-clr.md)|Fügt Elemente in einer bestimmten Position hinzu.|  
|[vector::pop\_back](../dotnet/vector-pop-back-stl-clr.md)|Entfernt das letzte Element.|  
|[vector::push\_back](../dotnet/vector-push-back-stl-clr.md)|Fügt ein neues letzte Element hinzu.|  
|[vector::rbegin](../dotnet/vector-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[vector::rend](../dotnet/vector-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[vector::reserve](../dotnet/vector-reserve-stl-clr.md)|Stellt eine minimale Zunahmekapazität für den Container sicher.|  
|[vector::resize](../dotnet/vector-resize-stl-clr.md)|Ändert die Anzahl der Elemente.|  
|[vector::size](../dotnet/vector-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[vector::swap](../dotnet/vector-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[vector::to\_array](../dotnet/vector-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[vector::vector](../dotnet/vector-vector-stl-clr.md)|Erstellt ein container\-Objekt.|  
  
|Eigenschaft|**Beschreibung**|  
|-----------------|----------------------|  
|[vector::back\_item](../dotnet/vector-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[vector::front\_item](../dotnet/vector-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[vector::operator](../dotnet/vector-operator-stl-clr.md)|Greift auf ein Element in einer angegebenen Position zu.|  
|[operator\!\= \(vector\)](../dotnet/operator-inequality-vector-stl-clr.md)|Bestimmt, ob ein `vector`\-Objekt nicht gleich ein anderes `vector`\-Objekt ist.|  
|[operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)|Bestimmt, ob ein `vector`\-Objekt kleiner als ein anderes `vector`\-Objekt ist.|  
|[operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Bestimmt, ob ein `vector`\-Objekt maximal ein anderes `vector`\-Objekt ist.|  
|[operator\=\= \(vector\)](../dotnet/operator-equality-vector-stl-clr.md)|Bestimmt, ob ein `vector`\-Objekt ein anderes Objekt gleich `vector` ist.|  
|[operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)|Bestimmt, ob ein `vector`\-Objekt größer als ein anderes `vector`\-Objekt ist.|  
|[operator\>\= \(vector\)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Bestimmt, ob ein `vector`\-Objekt größer oder gleich einem anderen `vector`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|<xref:System.Collections.IEnumerable>|Sequenz durch Elemente.|  
|<xref:System.Collections.ICollection>|Unbegrenztes Beibehalten Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Sequenz von typisierten Elemente.|  
|<xref:System.Collections.Generic.ICollection`1>|Unbegrenztes Beibehalten Gruppe typisierten Elemente bei.|  
|<xref:System.Collections.Generic.IList`1>|Maintain bestellte Gruppe typisierten Elemente.|  
|IVectorValue \<\>|Warten Sie generischen Container.|  
  
## Hinweise  
 Das Objekt belegt und gibt die Sequenz für Speicher frei, die durch ein gespeichertes Array Elemente `Value` steuert, das bei Bedarf vergrößert.  Erhöhung tritt auf, sodass die Kosten des Anfügens eines neuen Elements konstante Zeit amortisiert werden.  Das heißt, erhöhen sich die Kosten des Hinzufügens von Elementen am Ende nicht im Durchschnitt wie die Länge der Sequenz gesteuerten erhöht wird.  Daher ist ein Vektor gut für den zugrunde liegenden Container für Vorlagenklasse [Stapel](../dotnet/stack-stl-clr.md).  
  
 `vector` unterstützt Iteratoren mit wahlfreier Zugriff, dass Sie ein Element verweisen kann, das direkt [vector::size](../dotnet/vector-size-stl-clr.md)`() - 1` für das letzte \(Hintergrundfarbe\) Element seine numerische Position angegeben und Null für das erste Element \(vordere\) zählen.  Dies bedeutet auch, dass ein Vektor gut für den zugrunde liegenden Container für Vorlagenklasse [priority\_queue](../dotnet/priority-queue-stl-clr.md) ist.  
  
 Ein Vektoriterator speichert ein Handle auf dem zugeordneten Vektorobjekt, zusammen mit der die Neigung des Elements, das sie festgelegt werden.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Durch Neigen eines Vektorelements ist dieselbe wie seine Position.  
  
 Das Einfügen oder Löschen von Elementen können den Elementwert ändern, der an einer angegebenen Position wird gespeichert, sodass der Wert, der durch einen Iterator festgelegt ist, ändern. \(Der Container kann Elemente muss auf oder ab kopieren, um ein Loch vor einer Einfügung zu erstellen oder ein Loch nach einem Löschvorgang auszufüllen.\) Trotzdem bleibt ein Vektoriterator gültig, solange die Neigung im Bereich `[0,` [vector::size](../dotnet/vector-size-stl-clr.md)`()]` ist.  Darüber hinaus wird ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- sofern die Neigung nicht gleich `size()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [Stapel](../dotnet/stack-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)