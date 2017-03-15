---
title: "Avoidance of Heap Contention | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "heap contention"
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Avoidance of Heap Contention
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die standardmäßige Zeichenfolgenmanager, die von MFC und von ATL bereitgestellt werden, sind einfache Wrapper auf einen globalen Heaps.  Dieser globale Heap ist vollständig threadsicher und bedeutet, dass mehrere Threads Speicher von ihm gleichzeitig zuordnen und freigeben können, ohne den Heap zu beschädigen.  Um die Threadsicherheit bereitzustellen, muss der Heap Zugriff auf serialisieren.  Dies wird normalerweise mit einem kritischen Abschnitt oder einer ähnlichen Sperrung erreicht.  Wann immer zwei Threads versuchen, auf den Heap gleichzeitig zugreifen, ist ein Thread blockiert, bis die anderen Anforderungen des Threads beendet ist.  Für viele Anwendungen tritt diese Situation selten auf und die Auswirkungen auf die Leistung der Sperrung des Heaps sind geringfügig.  Für Anwendungen, die häufig zugreifen, können der Heap aus der mehrere Konflikt für die Sperre des Heaps kann der Anwendung verursachen, langsamer als auszuführen, wenn er singlethreaded war \(sogar auf Computern mit Unterstützung mehrerer CPUs\).  
  
 Anwendungen, die [CStringT](../atl-mfc-shared/reference/cstringt-class.md) verwenden, sind für Heapkonflikt besonders anfällig, da Vorgänge auf `CStringT`\-Objekte häufig Neuzuordnung des Zeichenfolgenpuffers erfordern.  
  
 Eine Möglichkeit, Heapkonflikt zwischen Threads zu mindern ist, jeden Thread Zeichenfolgen aus einem privaten, lokalen Heap zuordnen können.  Solange die Zeichenfolgen, die mit der Belegungsfunktion eines bestimmten Threads zugeordnet werden, nur in diesem Thread verwendet werden, muss die Belegungsfunktion, nicht threadsicher ist.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht eine Threadprozedur, die den eigenen privaten Nicht\-ThreadSAFE\-Heap zur Verwendung für Zeichenfolgen in diesem Thread zuordnet:  
  
 [!CODE [NVC_ATLMFC_Utilities#182](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#182)]  
  
## Kommentare  
 Mehrere Threads können mithilfe der gleichen Threadprozedur ausgeführt werden, aber, da jeder Thread über einen eigenen Heap hat, gibt es keinen Konflikt zwischen Threads.  Darüber hinaus führt der Tatsache, dass jeder Heap nicht threadsicher ist, eine messbare Leistungszunahme, auch wenn nur eine Kopie des Threads ausgeführt wird.  Dies ist das Ergebnis des Heaps nicht mit der teuren ineinandergegriffenen anhand der Zugriff zu schützen, Vorgänge, sich.  
  
 Für eine komplexere Threadprozedur kann es praktisch, einen Zeiger auf Zeichenfolgenmanager des Threads in einem Slot für lokalen Threadspeicher \(TLS\) zu speichern.  Dadurch können andere Funktionen, die von der Threadprozedur aufgerufen werden, um auf den Zeichenfolgenmanager des Threads auf.  
  
## Siehe auch  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)