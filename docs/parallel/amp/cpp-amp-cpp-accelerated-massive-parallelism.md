---
title: "C++ AMP (C++ Accelerated Massive Parallelism)"
ms.custom: na
ms.date: "12/16/2016"
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
  - "C++ Accelerated Massive Parallelism, Erste Schritte"
  - "C++ AMP (siehe C++ Accelerated Massive Parallelism)"
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 22
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# C++ AMP (C++ Accelerated Massive Parallelism)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\(C\+\+ AMP Accelerated Massive Parallelism\) beschleunigt die Ausführung von C\+\+\-Code, indem die Vorteile Daten parallel verarbeitender Hardware, beispielsweise ein Grafikprozessor \(Graphics Processing Unit, GPU\) auf einer separaten Grafikkarte, genutzt werden.  Das C\+\+ AMP\-Programmiermodell enthält Unterstützung für mehrdimensionale Arrays, Indizierung, Arbeitsspeicherübertragung und Tiling.  Außerdem umfasst es eine Bibliothek mathematischer Funktionen.  Mithilfe von C\+\+ AMP\-Sprachenerweiterungen können Sie steuern, wie Daten von der CPU auf die GPU bzw. zurück verschoben werden.  
  
## Verwandte Themen  
  
|Titel|**Beschreibung**|  
|-----------|----------------------|  
|[Übersicht über C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md)|Beschreibt die Hauptfunktionen von C\+\+ AMP und der mathematischen Bibliothek.|  
|[Verwenden von Lambdas, Function\-Objekten und eingeschränkten Funktionen](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Beschreibt, wie Lambda\-Ausdrücke, Funktionsobjekte und eingeschränkte Funktionen in Aufrufen der [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)\-Methode verwendet werden.|  
|[Verwenden von Kacheln](../../parallel/amp/using-tiles.md)|Beschreibt, wie Unterteilungen verwendet werden, um den C\+\+ AMP\-Code beschleunigen.|  
|[Verwenden von accelerator\-Objekten und accelerator\_view\-Objekten](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Beschreibt, wie die Ausführung des Codes auf der GPU mithilfe von Beschleunigern angepasst werden kann.|  
|[Verwenden von C\+\+ AMP in Windows Store\-Apps](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Beschreibt, wie C\+\+ AMP in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] \-Apps verwendet wird, die Windows\-Runtime\-Typen verwenden.|  
|[Grafiken \(C\+\+ AMP\)](../../parallel/amp/graphics-cpp-amp.md)|Beschreibt, wie die C\+\+ AMP\-Grafikbibliothek verwendet wird.|  
|[Exemplarische Vorgehensweise: Matrixmultiplikation](../../parallel/amp/walkthrough-matrix-multiplication.md)|Veranschaulicht die Matrixmultiplikation mithilfe von C\+\+ AMP\-Code und Unterteilung.|  
|[Exemplarische Vorgehensweise: Debuggen einer C\+\+ AMP\-Anwendung](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Erklärt, wie eine Anwendung erstellt und gedebuggt wird, die parallele Reduzierung verwendet, um ein großes Array von ganzen Zahlen aufzusummieren.|  
  
## Verweis  
 [Referenz \(C\+\+ AMP\)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [tile\_static\-Schlüsselwort](../../cpp/tile-static-keyword.md)  
  
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)  
  
## Weitere Ressourcen  
 [Blogbeitrag zu paralleler Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/?LinkId=238472)  
  
 [C\+\+ AMP\-Beispielprojekte zum Download](http://go.microsoft.com/fwlink/p/?LinkId=248508)  
  
 [Analyzing C\+\+ AMP Code with the Concurrency Visualizer](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)