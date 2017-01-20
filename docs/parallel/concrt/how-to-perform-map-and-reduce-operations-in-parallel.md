---
title: "Gewusst wie: Paralleles Ausf&#252;hren von Zuordnungs- und Reduzierungsoperationen"
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
  - "Parallel_transform-Funktion, Beispiel:"
  - "Parallele Zuordnung und Reduzierung, Beispiel"
  - "Parallel_reduce-Funktion, Beispiel:"
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Paralleles Ausf&#252;hren von Zuordnungs- und Reduzierungsoperationen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie Sie die [parallel_transform](../Topic/parallel_transform%20Function.md) und [concurrency::parallel_reduce](../Topic/parallel_reduce%20Function.md) Algorithmen und [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) Klasse, um die Vorkommen der Wörter in Dateien zu zählen.  
  
 Ein *Karte* -Vorgang gilt eine Funktion für jeden Wert in einer Sequenz. Ein *reduzieren* Vorgang kombiniert die Elemente einer Sequenz in einen Wert. Sie können die Standardvorlagenbibliothek (STL) [std::transform](../Topic/transform.md)[Std:: Accumulate](../Topic/accumulate.md) Klassen zum Ausführen von Zuordnungs- und Vorgänge zu reduzieren. Zur Verbesserung der Leistung bei vielen Problemen können Sie mit dem `parallel_transform`-Algorithmus parallel den Zuordnungsvorgang und mit dem `parallel_reduce`-Algorithmus parallel den Reduzierungsvorgang ausführen. In einigen Fällen können Sie mit `concurrent_unordered_map` die Zuordnung und Reduzierung in einem Vorgang durchführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Vorkommen von Wörtern in Dateien gezählt. Er verwendet [Std:: vector](vector%20Class.md) zur Darstellung des Inhalts von zwei Dateien. Der Zuordnungsvorgang berechnet das Vorkommen von jedem Wort in jedem Vektor. Der Reduzierungsvorang zählt die Wörter in den zwei Vektoren zusammen.  
  
 [!CODE [concrt-parallel-map-reduce#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-map-reduce#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt bzw. Fügen Sie ihn in eine Datei mit dem Namen `parallel-map-reduce.cpp` und dann den folgenden Befehl in einer Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc Parallel-Map-reduce.cpp**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 In diesem Beispiel können Sie mit der in concurrent_unordered_map.h definierten `concurrent_unordered_map`-Klasse die Zuordnung und Reduzierung in einem Vorgang durchführen.  
  
 [!CODE [concrt-parallel-map-reduce#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-map-reduce#2)]  
  
 In der Regel wird nur die äußere oder die innere Schleife parallel ausgeführt. Führen Sie die innere Schleife parallel aus, wenn Sie über relativ wenige Dateien mit vielen Wörtern verfügen. Führen Sie die äußere Schleife parallel aus, wenn Sie über relativ viele Dateien mit wenigen Wörtern verfügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallel_transform-Funktion](../Topic/parallel_transform%20Function.md)   
 [Parallel_reduce-Funktion](../Topic/parallel_reduce%20Function.md)   
 [Concurrent_unordered_map-Klasse](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
