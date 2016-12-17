---
title: "allocator-Klasse"
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
  - "std::allocator"
  - "allocator"
  - "memory/std::allocator"
  - "std.allocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator-Klasse"
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# allocator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das die Speicherbelegung und \-freigabe für Objektarrays des Typs **Typ** verwaltet. Ein Objekt der Klasse **allocator** ist das Standardzuweisungsobjekt, das in den Konstruktoren für verschiedene Containervorlagenklassen in der C\+\+\-Standardbibliothek angegeben ist.  
  
## Syntax  
  
```  
  
template <class   
Type  
>  
class allocator  
  
```  
  
#### Parameter  
 *Typ*  
 Der Objekttyp, für den der Speicher zugewiesen bzw. dessen Zuweisung aufgehoben wird.  
  
## Hinweise  
 Alle Standardvorlagenbibliothek\-Container verfügen über einen Vorlagenparameter, der auf **allocator** zurückgesetzt wird. Durch das Erstellen eines Containers mit einer benutzerdefinierten Zuweisung erhalten Sie die Kontrolle über die Zuweisung und können Element des Containers freisetzen.  
  
 Beispielsweise kann ein Zuweisungsobjekt Speicher in einem privaten Heap oder im freigegebenen Arbeitsspeicher zuweisen oder für kleine oder große Objektgrößen optimieren. Es könnte auch über die von ihm bereitgestellten Typdefinitionen angeben, dass über spezielle Accessor\-Objekte auf Elemente zugegriffen wird, die den freigegebenen Arbeitsspeicher verwalten, oder dass eine automatische Garbage Collection ausgeführt wird. Daher sollte eine Klasse, die den Speicher mithilfe eines Zuweisungsobjekts zuweist, diese Typen für das Deklarieren von Zeiger\- und Verweisobjekten verwenden, wie dies bei den Containern in der C\+\+\-Standardbibliothek der Fall ist.  
  
 **\(nur C\_\+\+98\/03\)** Wenn Sie eine Ableitung aus einer Zuweisungsklasse vornehmen, müssen Sie eine [rebind](../Topic/allocator::rebind.md)\-Struktur bereitstellen, deren „`_Other` typedef“ Ihre neue abgeleitete Klasse referenziert.  
  
 Daher definiert eine Zuweisung die folgenden Typen:  
  
-   [pointer](../Topic/allocator::pointer.md) verhält sich wie ein Zeiger auf **Type**.  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md) verhält sich wie ein const\-Zeiger auf **Type**.  
  
-   [reference](../Topic/allocator::reference.md) verhält sich wie ein Verweis auf **Type**.  
  
-   [const\_reference](../Topic/allocator::const_reference.md) verhält sich wie ein const\-Verweist auf **Type**.  
  
 Diese **Type**n geben das Format an, das Zeiger und Verweise für zugewiesene Elemente verwenden müssen. \([allocator::pointer](../Topic/allocator::pointer.md) entspricht nicht unbedingt **Type**\* für alle Zuweisungsobjekte, obwohl es über diese offensichtliche Definition für die Klasse **allocator** verfügt.\)  
  
 **C\+\+11 und höher:**  Verwenden Sie zum Aktivieren von „move“\-Vorgängen in Ihrer Zuweisung die minimale Zuweisungsschnittstelle, und implementieren Sie den Kopierkonstruktor „\=\= and \!\=“, Operatoren, „allocate“ und „deallocate“. Weitere Informationen und ein Beispiel finden Sie unter [Allokatoren](../standard-library/allocators.md).  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[Zuweisung](../Topic/allocator::allocator.md)|Zum Erstellen von `allocator`\-Objekten verwendete Konstruktoren.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator::const_pointer.md)|Ein Typ, der einen konstanten Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[const\_reference](../Topic/allocator::const_reference.md)|Ein Typ, der einen konstanten Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[difference\_type](../Topic/allocator::difference_type.md)|Ein ganzzahliger Typ mit Vorzeichen, der die Differenz zwischen Werten von Zeigern und dem Typ des Objekts, das von der Zuweisung verwaltet wird, darstellen kann.|  
|[pointer](../Topic/allocator::pointer.md)|Ein Typ, der einen Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[Verweis](../Topic/allocator::reference.md)|Ein Typ, der einen Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[size\_type](../Topic/allocator::size_type.md)|Ein ganzzahliger Typ ohne Vorzeichen, der die Länge einer beliebigen Sequenz darstellen kann, die ein Objekt der Vorlagenklasse `allocator` zuordnen kann.|  
|[value\_type](../Topic/allocator::value_type.md)|Ein Typ, der von der Zuweisung verwaltet wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Adresse](../Topic/allocator::address.md)|Sucht die Adresse eines Objekts, dessen Wert angegeben wird.|  
|[allocate](../Topic/allocator::allocate.md)|Ordnet einen Speicherblock zu, der groß genug ist, um mindestens eine angegebene Anzahl von Elementen zu speichern.|  
|[Konstrukt](../Topic/allocator::construct.md)|Erstellt eine bestimmte Art von Objekt an einer bestimmten Adresse, die mit einem angegebenen Wert initialisiert wird.|  
|[Aufheben der Zuordnung](../Topic/allocator::deallocate.md)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
|[destroy](../Topic/allocator::destroy.md)|Ruft einen Objektdestruktor auf, ohne die Zuordnung des Speicherplatzes aufzuheben, an dem Objekt gespeichert wurde.|  
|[max\_size](../Topic/allocator::max_size.md)|Gibt die Anzahl der Elemente vom Typ `Type` zurück, die von einem Objekt der Klasse `allocator` zugeordnet werden konnten, bevor der freie Speicherplatz verbraucht ist.|  
|[rebind](../Topic/allocator::rebind.md)|Eine Struktur, die eine Zuweisung für Objekt eines Typs zum Zuweisen von Speicher für Objekte des anderen Typs ermöglicht.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/allocator::operator=.md)|Weist ein `allocator` zu einem anderen `allocator`\-Objekt zu.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)