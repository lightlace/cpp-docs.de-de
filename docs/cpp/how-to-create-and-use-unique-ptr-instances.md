---
title: "Gewusst wie: Erstellen und Verwenden von unique_ptr-Instanzen"
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
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen und Verwenden von unique_ptr-Instanzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Zeiger eines [unique\_ptr](../standard-library/unique-ptr-class.md)\-Objekts wird nicht freigegeben.  Er kann nicht in ein anderes `unique_ptr`\-Objekt kopiert, als Wert an eine Funktion übergeben oder in einem STL\-Algorithmus \(Standardvorlagenbibliothek\) verwendet werden, für den Kopien erforderlich sind.  Ein `unique_ptr`\-Objekt kann nur verschoben werden.  Dies bedeutet, dass der Besitz der Arbeitsspeicherressource einem anderen `unique_ptr`\-Objekt übertragen wird und das ursprüngliche `unique_ptr`\-Objekt diese Ressource nicht mehr besitzt.  Es empfiehlt sich, ein Objekt auf einen Besitzer zu beschränken, da mehrere Besitzer die Komplexität der Programmlogik erhöhen.  Wenn Sie einen intelligenten Zeiger für ein einfaches C\+\+\-Objekt benötigen, verwenden Sie daher `unique_ptr`. Wenn Sie ein `unique_ptr`\-Objekt erstellen, verwenden Sie die [make\_unique](../Topic/make_unique.md)\-Hilfsfunktion.  
  
 Das folgende Diagramm veranschaulicht die Eigentumsübertragung zwischen zwei `unique_ptr`\-Instanzen.  
  
 ![Besitz von unique&#95;ptr wird verschoben](../cpp/media/unique_ptr.png "unique\_ptr")  
  
 `unique_ptr` wird `<memory>`\-Header in STL definiert.  Das Objekt ist genau so effizient wie ein unformatierter Zeiger und kann in STL\-Containern verwendet werden.  Das Hinzufügen von `unique_ptr`\-Instanzen zu STL\-Containern ist effizient, da der Bewegungskonstruktor des `unique_ptr`\-Objekts einen Kopiervorgang entfallen lässt.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie `unique_ptr`\-Instanzen erstellt und zwischen Funktionen übergeben werden.  
  
 [!CODE [stl_smart_pointers#210](../CodeSnippet/VS_Snippets_Cpp/stl_smart_pointers#210)]  
  
 Diese Beispiele zeigen diese grundlegende Eigenschaft des `unique_ptr`\-Objekts: Es kann verschoben, jedoch nicht kopiert werden. "Wird verschoben" überträgt den Besitz einem neuen `unique_ptr`\-Objekt und setzt das alte `unique_ptr`\-Objekt zurück.  
  
## Beispiel  
 Im folgenden Beispiel wird die Erstellung von `unique_ptr`\-Instanzen und ihre Verwendung in einem Vektor dargestellt.  
  
 [!CODE [stl_smart_pointers#211](../CodeSnippet/VS_Snippets_Cpp/stl_smart_pointers#211)]  
  
 Im Bereich der for\-Schleife wird das `unique_ptr`\-Objekt durch einen Verweis übergeben.  Wenn Sie versuchen, das Objekt als Wert zu übergeben, löst der Compiler einen Fehler aus, da der `unique_ptr`\-Kopierkonstruktor gelöscht wurde.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `unique_ptr`\-Objekt initialisiert wird, das ein Klassenmember ist.  
  
 [!CODE [stl_smart_pointers#212](../CodeSnippet/VS_Snippets_Cpp/stl_smart_pointers#212)]  
  
## Beispiel  
 Sie können [make\_unique](../Topic/make_unique.md) zum Erstellen eines `unique_ptr`\-Objekts für ein Array verwenden. Sie können `make_unique` jedoch nicht verwenden, um die Arrayelemente zu initialisieren.  
  
 [!CODE [stl_smart_pointers#213](../CodeSnippet/VS_Snippets_Cpp/stl_smart_pointers#213)]  
  
 Weitere Beispiele finden Sie unter [make\_unique](../Topic/make_unique.md).  
  
## Siehe auch  
 [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)   
 [make\_unique](../Topic/make_unique.md)