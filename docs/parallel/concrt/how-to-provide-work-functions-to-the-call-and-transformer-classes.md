---
title: "Gewusst wie: Bereitstellen von Arbeitsfunktionen f&#252;r die call- und transformer-Klassen | Microsoft Docs"
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
  - "call-Klasse, Beispiel"
  - "Verwenden der Transformer-Klasse [Concurrency Runtime]"
  - "Verwenden der Call-Klasse [Concurrency Runtime]"
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Bereitstellen von Arbeitsfunktionen f&#252;r die call- und transformer-Klassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden mehrere Möglichkeiten veranschaulicht, Arbeitsfunktionen für die [concurrency::call](../../parallel/concrt/reference/call-class.md)\-Klasse und die [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)\-Klasse bereitzustellen.  
  
 Im ersten Beispiel wird gezeigt, wie ein Lambda\-Ausdruck an ein `call`\-Objekt übergeben wird.  Im zweiten Beispiel wird gezeigt, wie ein Funktionsobjekt an ein `call`\-Objekt übergeben wird.  Im dritten Beispiel wird gezeigt, wie eine Klassenmethode an ein `call`\-Objekt gebunden wird.  
  
 Zu Illustrationszwecken wird in allen Beispielen dieses Themas die `call`\-Klasse verwendet.  Ein Beispiel, in dem die `transformer`\-Klasse verwendet wird, finden Sie unter [Gewusst wie: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## Beispiel  
 Im folgenden Beispiel wird aufgezeigt, wie die `call`\-Klasse häufig verwendet wird.  In diesem Beispiel wird eine Lambda\-Funktion an den `call`\-Konstruktor übergeben.  
  
 [!CODE [concrt-call-lambda#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-call-lambda#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **13 squared is 169.**   
## Beispiel  
 Das folgende Beispiel ähnelt dem vorherigen mit der Ausnahme, dass die `call`\-Klasse zusammen mit einem Funktionsobjekt \(Funktionselement\) verwendet wird.  
  
 [!CODE [concrt-call-functor#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-call-functor#1)]  
  
## Beispiel  
 Das folgende Beispiel ähnelt dem vorherigen Beispiel, mit dem Unterschied, dass die [std::bind1st](../Topic/bind1st%20Function.md)\-Funktion und die [std::mem\_fun](../Topic/mem_fun%20Function.md)\-Funktion zum Binden eines `call`\-Objekts an eine Klassenmethode verwendet werden.  
  
 Verwenden Sie diese Technik anstatt des Funktionsaufrufoperators, `operator()`, wenn Sie ein `call`\- oder `transformer`\-Objekt an eine bestimmte Klassenmethode binden möchten.  
  
 [!CODE [concrt-call-method#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-call-method#1)]  
  
 Sie können auch einem [std::function](../../standard-library/function-class.md)\-Objekt das Ergebnis der `bind1st`\-Funktion zuweisen oder das `auto`\-Schlüsselwort verwenden \(siehe folgendes Beispiel\).  
  
 [!CODE [concrt-call-method#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-call-method#2)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `call.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc call.cpp**  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Gewusst wie: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [call\-Klasse](../../parallel/concrt/reference/call-class.md)   
 [transformer\-Klasse](../../parallel/concrt/reference/transformer-class.md)