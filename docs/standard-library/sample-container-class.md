---
title: "Sample Container-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "container-Klassen"
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Sample Container-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als Beispiel funktioniert nicht für Container, die in der C++-Standardbibliothek verwendet. Weitere Informationen finden Sie unter [STL-Containern](../standard-library/stl-containers.md).  
  
 Beschreibt ein Objekt, das eine Elementsequenz variabler Länge Sequenz von Elementen, in der Regel vom Typ steuert **Ty**. Die Folge ist unterschiedlich, abhängig von der tatsächlichen Container gespeichert.  
  
 Eine Container-Konstruktor oder Member-Funktion möglicherweise Anlass Aufruf des Konstruktors **Ty**(**const Ty &**) oder die Funktion **Ty::operator =**(**const Ty &**). Wenn solch ein Aufruf eine Ausnahme auslöst, wird das Containerobjekt verpflichtet, um die Integrität beizubehalten, und jede Ausnahme erneut auslösen, fängt. Sie können sicher austauschen, zuweisen, löschen oder ein Container-Objekt zerstört, nachdem sie eine dieser Ausnahmen auslöst. Im Allgemeinen, Vorhersagen nicht jedoch andernfalls den Zustand der vom Container-Objekt Sequenz.  
  
 Einige zusätzliche Vorsichtsmaßnahmen:  
  
-   Wenn der Ausdruck **~ Ty** eine Ausnahme auslöst, der resultierende Status der Container-Objekt ist nicht definiert.  
  
-   Wenn der Container ein Zuweisungsobjekt speichert *al*, und *al* löst eine Ausnahme aufgrund eines Aufrufs von anderen als *al***.allocate**, der resultierende Status der Container-Objekt ist nicht definiert.  
  
-   Wenn der Container ein Funktionsobjekt speichert *Comp*, bestimmen, wie die kontrollierte Sequenz sortiert und *Comp* eine beliebige Ausnahme auslöst, der resultierende Status der Container-Objekt ist nicht definiert.  
  
 Der von Ihnen definierten Containerklassen STL erfüllen noch weitere Anforderungen, wie in den folgenden Abschnitten beschrieben.  
  
 Container-Vorlagenklasse [Liste](../standard-library/list-class.md) deterministisch und nützlich, Verhalten auch bei den oben beschriebenen Ausnahmen enthält. Z. B. wenn eine Ausnahme wird, wird beim Einfügen von einem ausgelöst oder mehreren Elementen, der Container unverändert, und die Ausnahme erneut ausgelöst wird.  
  
 Für *alle* der von Ihnen definierten Containerklassen STL, wenn eine Ausnahme, während die folgenden Memberfunktionen aufrufen ausgelöst wird:  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 der Container unverändert, und die Ausnahme erneut ausgelöst wird.  
  
 Für *alle* die Containerklassen von STL definiert, während die folgenden Memberfunktionen aufrufen wird keine Ausnahme ausgelöst:  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 Die Memberfunktion [Löschen](../standard-library/container-class-erase.md) löst eine Ausnahme aus, nur, wenn ein Kopiervorgang (Zuweisung oder Copy-Konstruktion) eine Ausnahme auslöst.  
  
 Darüber hinaus wird keine Ausnahme ausgelöst, während des Kopiervorgangs eines Iterators, der von einer Memberfunktion zurückgegeben wird.  
  
 Die Memberfunktion [Swap](../standard-library/container-class-swap.md) stellt zusätzliche Zusagen *alle* definiert, die von STL-Container-Klassen:  
  
-   Die Memberfunktion löst eine Ausnahme aus, nur dann, wenn der Container eine Zuweisung Objekt al, speichert und `al` löst eine Ausnahme aus, wenn Sie kopiert.  
  
-   Verweise, Zeiger und Iteratoren, mit denen Elemente der gesteuerten Sequenzen getauscht bleiben gültig.  
  
 Ein Objekt einer Container-Klasse, die von STL definiert reserviert und freigegeben Speicher für die gesteuerte Sequenz durch eine gespeicherte Objekt vom Typ `Alloc`, dem es sich gewöhnlich um einen Vorlagenparameter. Solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Klasse haben **Allocator \< Ty>**. Insbesondere `Alloc` muss der gleiche Typ wie **Alloc::rebind \< Value_type >:: andere**  
  
 Für *alle* von Ihnen definierten Containerklassen STL, die Memberfunktion **Alloc Get_allocator const;** eine Kopie der das gespeicherte Zuordnungsobjekt zurückgegeben. Beachten Sie, dass das gespeicherte Zuordnungsobjekt *nicht* kopiert, wenn das Containerobjekt zugewiesen wird. Alle Konstruktoren initialisieren den in gespeicherten Wert **Zuweisung**,  `Alloc` wenn der Konstruktor keine Zuweisungsparameter enthält.  
  
 Entsprechend dem C++-Standard kann eine Container-Klasse, die von STL definiert, die darstellen:  
  
-   Alle Objekte der Klasse `Alloc` Vergleich auf Gleichheit.  
  
-   Typ **Alloc::const_pointer** entspricht **const Ty \***.  
  
-   Typ **Alloc::const_reference** entspricht **const Ty &**.  
  
-   Typ **Alloc::pointer** entspricht **Ty \***.  
  
-   Typ **Alloc::reference** entspricht **Ty &**.  
  
 In dieser Implementierung werden jedoch Container nicht solche vereinfachende Annahmen zu machen. Daher arbeiten sie ordnungsgemäß mit Allocator-Objekte, die ehrgeizigere sind:  
  
-   Alle Objekte der Klasse `Alloc` muss nicht vergleichen gleich. (Sie können mehrere Speicher-Pools verwalten.)  
  
-   Typ **Alloc::const_pointer** müssen nicht identisch sein **const Ty \***. (Ein const-Zeiger kann auf eine Klasse sein.)  
  
-   Typ **Alloc::pointer** müssen nicht identisch sein **Ty \***. (Ein Zeiger kann auf eine Klasse sein.)  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: \< sample Container>  
  
## <a name="see-also"></a>Siehe auch  
 [\< Sample-Container>](../standard-library/sample-container.md)

