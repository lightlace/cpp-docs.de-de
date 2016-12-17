---
title: "&lt;memory&gt;"
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
  - "memory/std::<memory>"
  - "std.<memory>"
  - "<memory>"
  - "std::<memory>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memory-Header"
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
caps.latest.revision: 22
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# &lt;memory&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert eine Klasse, einen Operator und mehrere Vorlagen, die beim Zuordnen und Freigeben von Objekten helfen.  
  
## Syntax  
  
```  
  
#include <memory>  
  
```  
  
## Mitglieder  
  
### Funktionen  
  
|||  
|-|-|  
|[addressof](../Topic/addressof.md)|Ruft die echte Adresse eines Objekts ab.|  
|[align](../Topic/align.md)|Gibt einen Zeiger auf einen Bereich einer angegebenen Größe zurück, basierend auf der angegebenen Ausrichtung und der Startadresse.|  
|[allocate\_shared](../Topic/allocate_shared.md)|Erstellt `shared_ptr` auf Objekte, die einem angegebenen Typ mit einer angegebenen Zuordnung, zugeordnet und dafür erstellt werden.|  
|[checked\_uninitialized\_copy](../misc/checked-uninitialized-copy.md)|Wie `uninitialized_copy` allerdings wird die Verwendung eines überprüften Iterators als Ausgabeiterator erzwungen.|  
|[checked\_uninitialized\_fill\_n](../misc/checked-uninitialized-fill-n.md)|Wie `uninitialized_fill_n` allerdings wird die Verwendung eines überprüften Iterators als Ausgabeiterator erzwungen.|  
|[const\_pointer\_cast](../Topic/const_pointer_cast.md)|Konstantenumwandlung in `shared_ptr`.|  
|[declare\_no\_pointers](../Topic/declare_no_pointers.md)|Einem Garbage Collector wird mitgeteilt, dass die bei einer bestimmten Adresse startenden und in der angegebenen Blockgröße fallenden Zeichen keine nachweisbaren Zeiger enthalten.|  
|[declare\_reachable](../Topic/declare_reachable.md)|Der Garbage Collection wird mitgeteilt, dass die angegebene Adresse von zugewiesenem Speicher erreichbar ist.|  
|[default\_delete](../Topic/default_delete.md)|Es werden Objekte gelöscht, die `operator new` zugeordnet sind.  Kann mit `unique_ptr` verwendet werden.|  
|[dynamic\_pointer\_cast](../Topic/dynamic_pointer_cast.md)|Dynamische Umwandlung in `shared_ptr`.|  
|[get\_deleter](../Topic/get_deleter%20Function.md)|Rufen Sie den Deleter von `shared_ptr` ab.|  
|[get\_pointer\_safety](../Topic/get_pointer_safety.md)|Gibt den Typ der Zeigersicherheit zurück, der von einem Garbage Collector angenommen wird.|  
|[get\_temporary\_buffer](../Topic/get_temporary_buffer.md)|Weist temporären Speicher für eine Elementsequenz zu, die eine bestimmte Anzahl von Elementen nicht überschreitet.|  
|[make\_shared](../Topic/make_shared%20\(%3Cmemory%3E\).md)|Erstellt `shared_ptr`, das auf die zugeordneten Objekte zeigt, die mithilfe der Standardbelegung von keinen oder mehreren Argumenten erstellt werden, oder gibt es zurück.|  
|[make\_unique](../Topic/make_unique.md)|Erstellt [unique\_ptr](../standard-library/unique-ptr-class.md), das auf die zugeordneten Objekt zeigt, die von keinem oder mehreren Argumenten erstellt werden, oder gibt es zurück.|  
|[owner\_less](../Topic/owner_less.md)|Ermöglicht Mischvergleiche, die auf Besitz basieren, freigegebener und schwacher Zeiger.|  
|[pointer\_safety](../Topic/pointer_safety%20Enumeration.md)|Eine Enumeration aller möglichen Rückgabewerte für `get_pointer_safety`.|  
|[return\_temporary\_buffer](../Topic/return_temporary_buffer.md)|Gibt den temporären Speicher frei, der mithilfe der `get_temporary_buffer`\-Vorlagenfunktion zugeordnet wurde.|  
|[static\_pointer\_cast](../Topic/static_pointer_cast.md)|Statische Umwandlung in `shared_ptr`.|  
|[swap](../Topic/swap%20\(C++%20Standard%20Library\).md)|Tauschen Sie zwei `shared_ptr` oder `weak_ptr`\-Objekte.|  
|[unchecked\_uninitialized\_copy](../misc/unchecked-uninitialized-copy.md)|Wie `uninitialized_copy`, allerdings wird die Verwendung eines ungeprüften Iterators als Ausgabeiterator ermöglicht, wenn \_SECURE\_SCL\=1 definiert wird.|  
|[unchecked\_uninitialized\_fill\_n](../misc/unchecked-uninitialized-fill-n.md)|Wie `uninitialized_fill_n`, allerdings wird die Verwendung eines ungeprüften Iterators als Ausgabeiterator ermöglicht, wenn \_SECURE\_SCL\=1 definiert wird.|  
|[undeclare\_no\_pointers](../Topic/undeclare_no_pointers.md)|Einem Garbage Collector wird mitgeteilt, dass die Zeichen im Speicherblock, der von einem Basisadressenzeiger und \-blockgröße definiert wurde, jetzt möglicherweise nachweisbare Zeiger enthalten.|  
|[undeclare\_reachable](../Topic/undeclare_reachable.md)|`garbage_collector` wird mitgeteilt, dass eine angegebene Speicheradresse nicht erreichbar ist.|  
|[uninitialized\_copy](../Topic/uninitialized_copy.md)|Es werden Objekte aus einem angegebenen Eingabebereich in einen nicht initialisierten Zielbereich kopiert.|  
|[uninitialized\_copy\_n](../Topic/uninitialized_copy_n.md)|Eine Kopie einer angegebenen Anzahl von Elementen aus einem Eingabeiterator wird erstellt.  Die Kopien werden in einen Forward\-Iterator abgelegt.|  
|[uninitialized\_fill](../Topic/uninitialized_fill.md)|Objekte eines angegebenen Werts werden in einen nicht initialisierten Zielbereich kopiert.|  
|[uninitialized\_fill\_n](../Topic/uninitialized_fill_n.md)|Objekte einer angegebenen Anzahl von Elementen werden in einen nicht initialisierten Zielbereich kopiert.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/operator!=%20\(%3Cmemory%3E\).md)|Es wird auf Ungleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.|  
|[operator\=\=](../Topic/operator==%20\(%3Cmemory%3E\).md)|Es wird auf Gleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.|  
|[Operator \>\=](../Topic/operator%3E=%20\(%3Cmemory%3E\).md)|Es wird darauf getestet, dass Zuweisungsobjekt größer als oder gleich einem zweiten Zuweisungsobjekt einer bestimmten Klasse ist.|  
|[Operator \<](../Topic/operator%3C%20\(%3Cmemory%3E\).md)|Es wird getestet, ob ein Objekt kleiner als ein zweites Objekt einer bestimmten Klasse ist.|  
|[Operator \<\=](../Topic/operator%3C=%20\(%3Cmemory%3E\).md)|Es wird darauf getestet, dass ein Objekt kleiner als oder gleich einem zweiten Objekt einer bestimmten Klasse ist.|  
|[Operator \>](../Topic/operator%3E%20\(%3Cmemory%3E\).md)|Es wird getestet, ob ein Objekt größer als ein zweites Objekt einer bestimmten Klasse ist.|  
|[Operator \<\<](../Topic/operator%3C%3C%20\(%3Cmemory%3E\).md)|`shared_ptr`\-Einfüger|  
  
### Klassen  
  
|||  
|-|-|  
|[Zuweisung](../standard-library/allocator-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das die Speicherbelegung und \-freigabe für Objektarrays des Typs **Typ** verwaltet.|  
|[allocator\_traits](../standard-library/allocator-traits-class.md)|Beschreibt ein Objekt, das alle Informationen bestimmt, die für einen zuweisungsfähigen Container erforderlich ist.|  
|[auto\_ptr](../standard-library/auto-ptr-class.md)|Die Vorlagenklasse beschreibt ein Objekt, in dem ein Zeiger auf ein zugeordnetes Objekt des Typs **Type \*** gespeichert wird, das das Löschen des Objekts, auf das verwiesen wird, sicherstellt, wenn das einschließende auto\_ptr zerstört wird.|  
|[bad\_weak\_ptr](../standard-library/bad-weak-ptr-class.md)|Meldet eine ungültige weak\_ptr\-Ausnahme.|  
|[enabled\_shared\_from\_this](../standard-library/enable-shared-from-this-class.md)|Hilft bei der Erstellung von `shared_ptr`.|  
|[pointer\_traits](../standard-library/pointer-traits-struct.md)|Stellt Informationen bereit, die für ein Objekt der Vorlagenklasse `allocator_traits` erforderlich sind, um eine Zuweisung mit Zeigertyp `Ptr` zu beschreiben.|  
|[raw\_storage\_iterator](../standard-library/raw-storage-iterator-class.md)|Eine Adapterklasse, die bereitgestellt wird, um Algorithmen das Speichern ihrer Ergebnisse in nicht initialisiertem Speicher zu ermöglichen.|  
|[shared\_ptr](../standard-library/shared-ptr-class.md)|Umschließt einen intelligenten Zeiger mit Verweiszählung um ein dynamisch zugeordnetes Objekt.|  
|[unique\_ptr](../standard-library/unique-ptr-class.md)|Es wird ein Zeiger auf ein Objekt in Besitz gespeichert.  Der Zeiger ist nicht im Besitz eines anderen `unique_ptr`\-Elements.  `unique_ptr` wird zerstört, wenn der Besitzer zerstört wird.|  
|[weak\_ptr](../standard-library/weak-ptr-class.md)|Umschließt einen schwach verknüpften Zeiger.|  
  
### Spezialisierungen  
  
|||  
|-|-|  
|[allocator\<void\>](../standard-library/allocator-void-class.md)|Eine Spezialisierung der Vorlagenklassenzuweisung zum Typ "void", die die einzigen Membertypen definiert, die in diesem speziellen Kontext sinnvoll sind.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)