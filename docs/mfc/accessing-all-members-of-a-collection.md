---
title: "Zugreifen auf alle Elemente einer Auflistung"
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
  - "MFC, Auflistungen"
  - "Enumerationen [MFC]"
  - "Enumeration von Auflistungen"
  - "Auflistungen, Zugriff"
  - "Auflistungsklassen, Zugriff auf Member"
  - "Arrays [C++], durchlaufen"
  - "Iteration, Auflistungen"
  - "Memberzugriff, Auflistungen"
  - "Listenauflistungsiterationen"
  - "MFC-Auflistungsklassen, Zugriff auf Member"
  - "Auflistungen, Schleifendurchlauf"
  - "Schleifenstrukturen, Schleifendurchlauf durch Auflistungen"
ms.assetid: 7bbae518-062e-4393-81f9-b22abd2e5f59
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Zugreifen auf alle Elemente einer Auflistung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-Arrayauflistungsklassen – sowohl die vorlagenbasierten als auch die nicht vorlagenbasierten – verwenden Indizes, um auf ihre Elemente zuzugreifen. Die MFC\-Listen\- und Zuordnungsauflistungsklassen – sowohl die vorlagenbasierten als auch die nicht vorlagenbasierten – verwenden einen Indikator vom Typ **POSITION** zum Beschreiben einer bestimmten Position in der Auflistung. Für den Zugriff auf einen oder mehrere Member dieser Auflistungen zunächst initialisieren Sie zunächst den Positionsindikator und übergeben dann diese Position wiederholt an die Auflistung und fordert Sie auf das nächste Element zurückzugeben. Die Auflistung ist nicht verantwortlich für die Verwaltung von Statusinformationen hinsichtlich des Fortschritts der Iteration. Diese Informationen werden im Positionsindikator gespeichert. Bei einer bestimmten Position ist die Auflistung jedoch dafür verantwortlich, das nächste Element zurückzugeben.  
  
 Die folgenden Verfahren zeigen, wie Sie die drei Haupttypen von Auflistungen, die mit MFC bereitgestellt werden, durchlaufen:  
  
-   [Durchlaufen eines Arrays](#_core_to_iterate_an_array)  
  
-   [Durchlaufen einer Liste](#_core_to_iterate_a_list)  
  
-   [Durchlaufen einer Zuordnung](#_core_to_iterate_a_map)  
  
### So durchlaufen Sie ein Array  
  
1.  Verwenden Sie die sequenziellen Indexzahlen mit der `GetAt`\-Memberfunktion:  
  
     [!CODE [NVC_MFCCollections#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#12)]  
  
     Dieses Beispiel verwendet ein typisiertes Zeigerarray, das enthält Zeiger auf `CPerson`\-Objekte enthält. Das Array wird von der Klasse `CObArray` abgeleitet, eine der nicht auf Vorlagen basierenden, vordefinierten Klassen.`GetAt` gibt einen Zeiger auf ein `CPerson`\-Objekt zurück. Für typisierte Zeigerauflistungsklassen – Arrays oder Listen – gibt der erste Parameter die Basisklasse an; der zweite Parameter gibt den zu speichernden Typ an.  
  
     Die `CTypedPtrArray`\-Klasse überlädt den **\[ \]**\-Operator, damit Sie die übliche tiefgestellte Array\-Syntax verwenden können, um auf Elemente eines Arrays zuzugreifen. Eine Alternative zur Anweisung im Hauptteil der obigen `for`\-Schleife sieht folgendermaßen aus:  
  
     [!CODE [NVC_MFCCollections#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#13)]  
  
     Dieser Operator ist in den **const**\- und nicht\-**const**\-Versionen vorhanden. Die **const**\-Version, die für **const**\-Arrays aufgerufen wird, können nur auf der rechten Seite einer Zuweisungsanweisung angezeigt werden.  
  
### So durchlaufen Sie eine Liste  
  
1.  Verwenden Sie die Memberfunktionen `GetHeadPosition` und `GetNext` zum Navigieren durch die Liste:  
  
     [!CODE [NVC_MFCCollections#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#14)]  
  
     Dieses Beispiel verwendet eine typisierte Zeigerliste, um Zeiger auf `CPerson`\-Objekte zu enthalten. Die List\-Deklaration ähnelt der für das Array in der Prozedur [So durchlaufen Sie ein Array](#_core_to_iterate_an_array), sie wird jedoch von der Klasse `CObList` abgeleitet.`GetNext` gibt einen Zeiger auf ein `CPerson`\-Objekt zurück.  
  
### So durchlaufen Sie eine Zuordnung  
  
1.  Verwenden Sie `GetStartPosition`, um an den Anfang der Zuordnung zu wechseln, und `GetNextAssoc`, um den nächsten Schlüssel und Wert wiederholt aus der Zuordnung abzurufen, wie im folgenden Beispiel gezeigt:  
  
     [!CODE [NVC_MFCCollections#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#15)]  
  
     Dieses Beispiel verwendet eine einfache Zuordnungsvorlage \(statt einer typisierten Zeigerauflistung\), die `CString`\-Schlüssel nutzt und Zeiger auf `CPerson`\-Objekte speichert. Wenn Sie Zugriffsfunktionen wie z. B. `GetNextAssoc` verwenden, bietet die Klasse Zeiger auf `CPerson`\-Objekte. Wenn Sie stattdessen eine der nicht auf Vorlagen basierten Zuordnungsauflistungen verwenden, müssen Sie den zurückgegebenen `CObject`\-Zeiger in einen Zeiger auf eine `CPerson` umwandeln.  
  
    > [!NOTE]
    >  Für nicht auf Vorlagen basierende Zuordnungen erfordert der Compiler einen Verweis auf einen `CObject`\-Zeiger im letzten Parameter für `GetNextAssoc`. Bei der Eingabe müssen Sie die Zeiger in diesen Typ umwandeln, wie im nächsten Beispiel gezeigt.  
  
     Die Vorlagenlösung ist einfacher und bietet eine bessere Typsicherheit. Der nicht auf Vorlagen basierende Code ist komplizierter, wie Sie hier sehen können:  
  
     [!CODE [NVC_MFCCollections#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#16)]  
  
 Weitere Informationen finden Sie unter [Löschen aller Objekte in einer CObject\-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md).  
  
## Siehe auch  
 [Auflistungen](../mfc/collections.md)