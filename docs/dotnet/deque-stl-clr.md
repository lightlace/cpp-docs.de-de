---
title: "deque (STL/CLR)"
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
  - "cliext::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/deque>-Header [STL/CLR]"
  - "<deque>-Header [STL/CLR]"
  - "deque-Klasse [STL/CLR]"
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# deque (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die wahlfreien Zugriff hat.  Mit dem Container `deque`, um eine Sequenz von Elementen zu verwalten, die wie ein zusammenhängender Block Speicher aussieht, die an jedem Ende ohne die Anforderung wächst oder verringern kann, alle verbleibenden Elemente zu kopieren.  Daher kann sie `double-ended queue` effizient implementieren. \(Daher der Name\).  
  
 In der unten stehenden Beschreibung, `GValue` ist das `Value` identisch, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Value^` dar.  
  
## Syntax  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### Parameter  
 GValue  
 Der generische Typ eines Elements in der Sequenz. gesteuerten  
  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[deque::const\_iterator](../dotnet/deque-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[deque::const\_reference](../dotnet/deque-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[deque::const\_reverse\_iterator](../dotnet/deque-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[deque::difference\_type](../dotnet/deque-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[deque::generic\_container](../dotnet/deque-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[deque::generic\_iterator](../dotnet/deque-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[deque::generic\_reverse\_iterator](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[deque::generic\_value](../dotnet/deque-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[deque::iterator](../dotnet/deque-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[deque::reference](../dotnet/deque-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[deque::reverse\_iterator](../dotnet/deque-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[deque::size\_type](../dotnet/deque-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[deque::value\_type](../dotnet/deque-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[deque::assign](../dotnet/deque-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[deque::at](../dotnet/deque-at-stl-clr.md)|Greift auf ein Element in einer angegebenen Position zu.|  
|[deque::back](../dotnet/deque-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[deque::begin](../dotnet/deque-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[deque::clear](../dotnet/deque-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[deque::deque](../dotnet/deque-deque-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[deque::empty](../dotnet/deque-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[deque::end](../dotnet/deque-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[deque::erase](../dotnet/deque-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[deque::front](../dotnet/deque-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[deque::insert](../dotnet/deque-insert-stl-clr.md)|Fügt Elemente in einer bestimmten Position hinzu.|  
|[deque::pop\_back](../dotnet/deque-pop-back-stl-clr.md)|Entfernt das letzte Element.|  
|[deque::pop\_front](../dotnet/deque-pop-front-stl-clr.md)|Entfernt das erste Element.|  
|[deque::push\_back](../dotnet/deque-push-back-stl-clr.md)|Fügt ein neues letzte Element hinzu.|  
|[deque::push\_front](../dotnet/deque-push-front-stl-clr.md)|Fügt ein neues erstes Element hinzu.|  
|[deque::rbegin](../dotnet/deque-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[deque::rend](../dotnet/deque-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[deque::resize](../dotnet/deque-resize-stl-clr.md)|Ändert die Anzahl der Elemente.|  
|[deque::size](../dotnet/deque-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[deque::swap](../dotnet/deque-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[deque::to\_array](../dotnet/deque-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
  
|Eigenschaft|**Beschreibung**|  
|-----------------|----------------------|  
|[deque::back\_item](../dotnet/deque-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[deque::front\_item](../dotnet/deque-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[deque::operator\!\=](../dotnet/deque-operator-inequality-stl-clr.md)|Bestimmt, ob zwei `deque`\-Objekte ungleich sind.|  
|[deque::operator](../dotnet/deque-operator-stl-clr.md)|Greift auf ein Element in einer angegebenen Position zu.|  
|[operator\< \(deque\)](../dotnet/operator-less-than-deque-stl-clr.md)|Bestimmt, ob ein `deque`\-Objekt kleiner als ein anderes `deque`\-Objekt ist.|  
|[operator\<\= \(deque\)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|Bestimmt, ob ein `deque`\-Objekt maximal ein anderes `deque`\-Objekt ist.|  
|[operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\=\= \(deque\)](../dotnet/operator-equality-deque-stl-clr.md)|Bestimmt, ob ein `deque`\-Objekt ein anderes Objekt gleich `deque` ist.|  
|[operator\> \(deque\)](../dotnet/operator-greater-than-deque-stl-clr.md)|Bestimmt, ob ein `deque`\-Objekt größer als ein anderes `deque`\-Objekt ist.|  
|[operator\>\= \(deque\)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|Bestimmt, ob ein `deque`\-Objekt größer oder gleich einem anderen `deque`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|<xref:System.Collections.IEnumerable>|Sequenz durch Elemente.|  
|<xref:System.Collections.ICollection>|Unbegrenztes Beibehalten Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Sequenz von typisierten Elemente.|  
|<xref:System.Collections.Generic.ICollection`1>|Unbegrenztes Beibehalten Gruppe typisierten Elemente bei.|  
|<xref:System.Collections.Generic.IList`1>|Maintain bestellte Gruppe typisierten Elemente.|  
|IDequeValue \<\>|Warten Sie generischen Container.|  
  
## Hinweise  
 Das Objekt belegt und gibt die Sequenz für Speicher frei, die durch ein gespeichertes Array von Handles steuert, die vorgesehene Blöcke `Value`\-Elemente.  Das Array nimmt bei Bedarf.  Erhöhung tritt auf, sodass die Kosten entweder mit Voranstellens oder des Anfügens eines neuen Elements konstante Zeit sind, und keine verbleibenden Elemente behindert werden.  Sie können ein Element an jedem Ende in der konstanten Zeit und ohne beunruhigende verbleibende Elemente auch entfernen.  Daher ist eine Doppelschlange gut für den zugrunde liegenden Container für Vorlagenklasse [queue](../dotnet/queue-stl-clr.md) oder Vorlagenklasse [Stapel](../dotnet/stack-stl-clr.md).  
  
 Ein `deque`\-Objekt unterstützt Iteratoren mit wahlfreier Zugriff, dass Sie ein Element verweisen kann, das direkt [deque::size](../dotnet/deque-size-stl-clr.md)`() - 1` für das letzte \(Hintergrundfarbe\) Element seine numerische Position angegeben und Null für das erste Element \(vordere\) zählen.  Dies bedeutet auch, dass eine Doppelschlange gut für den zugrunde liegenden Container für Vorlagenklasse [priority\_queue](../dotnet/priority-queue-stl-clr.md) ist.  
  
 Ein Doppelschlangeniterator speichert ein Handle auf dem zugeordneten Doppelschlangenobjekt, zusammen mit der die Neigung des Elements, das sie festgelegt werden.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Durch Neigen eines Doppelschlangenelements `not` ist unbedingt identisch seine Position.  Das erste Element hat schräges eingefügte null, hat das folgende schräges angefügte Element 1, aber der nächste vorangestellte Element verfügt schräges \-1.  
  
 Das Einfügen oder Löschen von Elementen an jedem Ende hat `not` ändern den Wert eines Elements, das bei jeder gültigen Neigung gespeichert wird.  Ein Innenelement Einfügen oder Löschen kann jedoch `can` Änderung Elementwert, der an einer angegebenen Neigung, sodass gespeichert werden, der Wert, der durch einen Iterator festgelegt ist, ändern. \(Der Container kann Elemente muss auf oder ab kopieren, um ein Loch vor einer Einfügung zu erstellen oder ein Loch nach einem Löschvorgang auszufüllen.\) Trotzdem bleibt ein Doppelschlangeniterator gültig, solange die Neigung ein gültiges Element festlegt.  Darüber hinaus wird ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- sofern die Neigung ungleich die Neigung für den Iterator ist, der von `end()` zurückgegeben wird.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Doppelschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [Stapel](../dotnet/stack-stl-clr.md)   
 [Vektor](../dotnet/vector-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)