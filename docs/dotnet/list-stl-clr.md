---
title: "list (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/list>-Header [STL/CLR]"
  - "<list>-Header [STL/CLR]"
  - "list-Klasse [STL/CLR]"
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine VARYINGLängen\-Folge von Elementen steuert, die bidirektionalen Zugriff hat.  Mit dem Container `list`, um eine Sequenz von Elementen als bidirektionale verknüpfte Liste von Knoten, jedes speichernde ein Element zu verwalten.  
  
 In der unten stehenden Beschreibung, `GValue` ist das `Value` identisch, es sei denn, das zweite ein Referenz\-Typ ist, in diesem Fall `Value^` dar.  
  
## Syntax  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[list::const\_iterator](../dotnet/list-const-iterator-stl-clr.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[list::const\_reference](../dotnet/list-const-reference-stl-clr.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[list::const\_reverse\_iterator](../dotnet/list-const-reverse-iterator-stl-clr.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[list::difference\_type](../dotnet/list-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[list::generic\_container](../dotnet/list-generic-container-stl-clr.md)|Der Typ der generischen Schnittstelle für den Container.|  
|[list::generic\_iterator](../dotnet/list-generic-iterator-stl-clr.md)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[list::generic\_reverse\_iterator](../dotnet/list-generic-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[list::generic\_value](../dotnet/list-generic-value-stl-clr.md)|Der Typ des Elements für die generische Schnittstelle für den Container.|  
|[list::iterator](../dotnet/list-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[list::reference](../dotnet/list-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[list::reverse\_iterator](../dotnet/list-reverse-iterator-stl-clr.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[list::size\_type](../dotnet/list-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[list::value\_type](../dotnet/list-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[list::assign](../dotnet/list-assign-stl-clr.md)|Ersetzt alle Elemente.|  
|[list::back](../dotnet/list-back-stl-clr.md)|Greift auf das letzte Element zu.|  
|[list::begin](../dotnet/list-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[list::clear](../dotnet/list-clear-stl-clr.md)|Entfernt alle Elemente.|  
|[list::empty](../dotnet/list-empty-stl-clr.md)|Testet, dass keine Elemente vorhanden sind.|  
|[list::end](../dotnet/list-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[list::erase](../dotnet/list-erase-stl-clr.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[list::front](../dotnet/list-front-stl-clr.md)|Greift auf das erste Element zu.|  
|[list::insert](../dotnet/list-insert-stl-clr.md)|Fügt Elemente in einer bestimmten Position hinzu.|  
|[list::list](../dotnet/list-list-stl-clr.md)|Erstellt ein container\-Objekt.|  
|[list::merge](../dotnet/list-merge-stl-clr.md)|Führt zwei geordnete kontrollierte Sequenzen zusammen.|  
|[list::pop\_back](../dotnet/list-pop-back-stl-clr.md)|Entfernt das letzte Element.|  
|[list::pop\_front](../dotnet/list-pop-front-stl-clr.md)|Entfernt das erste Element.|  
|[list::push\_back](../dotnet/list-push-back-stl-clr.md)|Fügt ein neues letzte Element hinzu.|  
|[list::push\_front](../dotnet/list-push-front-stl-clr.md)|Fügt ein neues erstes Element hinzu.|  
|[list::rbegin](../dotnet/list-rbegin-stl-clr.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[list::remove](../dotnet/list-remove-stl-clr.md)|Entfernt ein Element mit einem angegebenen Wert.|  
|[list::remove\_if](../dotnet/list-remove-if-stl-clr.md)|Entfernt Elemente, die einen bestimmten Test übergeben.|  
|[list::rend](../dotnet/list-rend-stl-clr.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[list::resize](../dotnet/list-resize-stl-clr.md)|Ändert die Anzahl der Elemente.|  
|[list::reverse](../dotnet/list-reverse-stl-clr.md)|Kehrt die gesteuerte Sequenz um.|  
|[list::size](../dotnet/list-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[list::sort](../dotnet/list-sort-stl-clr.md)|Sortiert die kontrollierte Sequenz.|  
|[list::splice](../dotnet/list-splice-stl-clr.md)|Erneuert Links zwischen Knoten.|  
|[list::swap](../dotnet/list-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
|[list::to\_array](../dotnet/list-to-array-stl-clr.md)|Kopiert die gesteuerte Sequenz zu einem neuen Array.|  
|[list::unique](../dotnet/list-unique-stl-clr.md)|Entfernt benachbarte Elemente, die einen angegebenen Test bestehen.|  
  
|Eigenschaft|**Beschreibung**|  
|-----------------|----------------------|  
|[list::back\_item](../dotnet/list-back-item-stl-clr.md)|Greift auf das letzte Element zu.|  
|[list::front\_item](../dotnet/list-front-item-stl-clr.md)|Greift auf das erste Element zu.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[list::operator\=](../dotnet/list-operator-assign-stl-clr.md)|Ersetzt die gesteuerte Sequenz.|  
|[operator\!\= \(list\)](../dotnet/operator-inequality-list-stl-clr.md)|Bestimmt, ob ein `list`\-Objekt nicht gleich ein anderes `list`\-Objekt ist.|  
|[operator\< \(list\)](../dotnet/operator-less-than-list-stl-clr.md)|Bestimmt, ob ein `list`\-Objekt kleiner als ein anderes `list`\-Objekt ist.|  
|[operator\<\= \(list\)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Bestimmt, ob ein `list`\-Objekt maximal ein anderes `list`\-Objekt ist.|  
|[operator\=\= \(list\)](../dotnet/operator-equality-list-stl-clr.md)|Bestimmt, ob ein `list`\-Objekt ein anderes Objekt gleich `list` ist.|  
|[operator\> \(list\)](../dotnet/operator-greater-than-list-stl-clr.md)|Bestimmt, ob ein `list`\-Objekt größer als ein anderes `list`\-Objekt ist.|  
|[operator\>\= \(list\)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Bestimmt, ob ein `list`\-Objekt größer oder gleich einem anderen `list`\-Objekt ist.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.ICloneable>|Ein Objekt duplizieren.|  
|<xref:System.Collections.IEnumerable>|Sequenz durch Elemente.|  
|<xref:System.Collections.ICollection>|Unbegrenztes Beibehalten Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Sequenz von typisierten Elemente.|  
|<xref:System.Collections.Generic.ICollection`1>|Unbegrenztes Beibehalten Gruppe typisierten Elemente bei.|  
|IListValue \<\>|Warten Sie generischen Container.|  
  
## Hinweise  
 Das Objekt belegt und gibt die Sequenz für Speicher frei, die, er während einzelner Knoten in einer bidirektionalen Linkliste steuert.  Sie weist Elemente neu indem die Links zwischen Knoten, nie ändert, indem der Inhalt von einem Knoten zum anderen kopiert.  Das bedeutet, dass Sie Elemente beunruhigende ohne verbleibende Elemente frei einfügen und löschen können.  Daher ist eine Liste gut für den zugrunde liegenden Container für Vorlagenklasse [queue](../dotnet/queue-stl-clr.md) oder Vorlagenklasse [Stapel](../dotnet/stack-stl-clr.md).  
  
 Ein `list`\-Objekt unterstützt bidirektionale Iteratoren, dass Sie zu benachbarten Elementen werden kann, dass ein Iterator angegeben werden, der ein Element in der Sequenz gesteuerten festlegt.  Ein spezieller Hauptknoten entspricht dem Iterator, der durch [list::end](../dotnet/list-end-stl-clr.md)`()` zurückgegeben wird.  Sie können diesen Iterator Dekrementieren, um das letzte Element der gesteuerten Sequenz erreicht, wenn vorhanden.  Sie können einen Listeniterator erhöhen, um den Hauptknoten erreicht, und vergleicht er dann gleich `end()`.  Sie können jedoch den Iterator nicht möglich, der von `end()` zurückgegeben wird.  
  
 Beachten Sie, dass Sie ein Listenelement nicht zugreifen können, das direkt die numerische Position angegeben wird \- das erfordert einen Iterator mit wahlfreier Zugriff.  Daher ist eine Liste `not`, das als zugrunde liegender Container für Vorlagenklasse [priority\_queue](../dotnet/priority-queue-stl-clr.md) verwendbar ist.  
  
 Ein Listeniterator speichert ein Handle auf dem zugeordneten Listenknoten, der wiederum ein Handle auf dem zugeordneten Container speichert.  Sie können Iteratoren nur mit ihren zugeordneten Containerobjekten verwenden.  Ein Listeniterator bleibt gültig, solange der zugehörige Listenknoten mit einer Liste zugeordnet wird.  Darüber hinaus ist ein gültiger dereferencable Iterator \- Sie können ihn verwenden, um auf den Elementwert zuzugreifen oder zu ändern, der festlegt wird \- solange er nicht gleich `end()` ist.  
  
 Ein Element Löschen oder entfernen, wird der Destruktor für den gespeicherten Wert auf.  Die Container Löschen eines Auflistungsobjekts, löscht alle Elemente.  Somit wird sichergestellt ein Container, dessen Elementtyp eine Verweisklasse, ist, dass keine Elemente den Container Beibehaltene Objekte.  Beachten Sie jedoch dem Container Handles `not` bewirkt, zerstören seine Elemente.  
  
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [Stapel](../dotnet/stack-stl-clr.md)   
 [Vektor](../dotnet/vector-stl-clr.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)