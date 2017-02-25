---
title: "Speicherverwaltung: Beispiele | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Zuordnen von Ressourcen"
  - "Arrays [C++], Speicherverwaltung"
  - "Datenstrukturen [C++]"
  - "Datenstrukturen [C++], Speicherbelegung"
  - "Beispiele [MFC], Speicherreservierung"
  - "Rahmenzuordnung"
  - "Heapzuordnung, Beispiele"
  - "Speicherbelegung [C++], Arrays"
  - "Speicherbelegung [C++], Datenstrukturen"
  - "Speicherbelegung [C++], Beispiele"
  - "Speicherbelegung [C++], Objekte"
  - "MFC [C++], Speicherverwaltung"
  - "Objekte [C++], Speicherbelegung"
  - "Objekte [C++], Speicherreservierung"
  - "Strukturspeicherbelegung"
  - "Typen [C++], Speicherreservierung"
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Speicherverwaltung: Beispiele
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, wie MFC Framezuordnungen und \-Heapbelegungen für alle drei typische Arten von Speicherbelegungen durchführen:  
  
-   [Ein Bytearray](#_core_allocation_of_an_array_of_bytes)  
  
-   [Eine Datenstruktur](#_core_allocation_of_a_data_structure)  
  
-   [Ein Objekt](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> Zuordnung eines Bytearrays  
  
#### Um ein Bytearray über den Frame zuordnen  
  
1.  Definieren Sie das Array wie durch den folgenden Code dargestellt.  Das Array wird automatisch gelöscht und angegeben sein Arbeitsspeicher frei, wenn die Arrayvariablen den Bereich beendet wird.  
  
     [!CODE [NVC_MFC_Utilities#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#1)]  
  
#### Um ein Bytearray \(bzw. jedes primitiven Datentyp\) auf dem Heap zuordnen  
  
1.  Verwenden Sie den Operator **neu** mit der Arraysyntax, die in diesem Beispiel gezeigt wird:  
  
     [!CODE [NVC_MFC_Utilities#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#2)]  
  
#### So Arrays vom Heap frei  
  
1.  Verwenden Sie den Operator **löschen**, wie folgt:  
  
     [!CODE [NVC_MFC_Utilities#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#3)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> Zuordnung einer Datenstruktur  
  
#### So einer Datenstruktur über den Frame zuordnen  
  
1.  Definieren Sie die Strukturvariable, wie folgt:  
  
     [!CODE [NVC_MFC_Utilities#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#4)]  
  
     Der Speicher, der durch die Struktur belegt wird, wird freigegeben, wenn der Bereich beendet.  
  
#### So Datenstrukturen auf dem Heap zuordnen  
  
1.  Verwenden Sie **neu**, um Datenstrukturen auf dem Heap zuzuordnen und **löschen**, um ihnen, wie dargestellt durch die folgenden Beispiele verwenden:  
  
     [!CODE [NVC_MFC_Utilities#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#5)]  
  
##  <a name="_core_allocation_of_an_object"></a> Zuordnung eines Objekts  
  
#### So fügen Sie ein Objekt über den Frame zuordnen  
  
1.  Deklarieren Sie das Objekt, wie folgt:  
  
     [!CODE [NVC_MFC_Utilities#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#6)]  
  
     Der Destruktor für das Objekt automatisch aufgerufen, wenn das Objekt den Bereich beendet wird.  
  
#### So fügen Sie ein Objekt auf dem Heap zuordnen  
  
1.  Verwenden Sie den Operator **neu**, der einem Zeiger auf das Objekt zurückgibt, um Objekte auf dem Heap zuzuordnen.  Verwenden Sie den Operator **löschen**, um sie zu löschen.  
  
     Die folgenden Heap\- und Framebeispiele wird davon ausgegangen, dass der Konstruktor `CPerson` keine Argumente akzeptiert.  
  
     [!CODE [NVC_MFC_Utilities#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#7)]  
  
     Wenn das Argument für den Konstruktor `CPerson` ein Zeiger auf `char` ist, wird die Anweisung für Framezuordnung:  
  
     [!CODE [NVC_MFC_Utilities#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#8)]  
  
     Die Anweisung für Heapreservierung ist:  
  
     [!CODE [NVC_MFC_Utilities#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#9)]  
  
## Siehe auch  
 [Speicherverwaltung: Heapbelegung](../mfc/memory-management-heap-allocation.md)