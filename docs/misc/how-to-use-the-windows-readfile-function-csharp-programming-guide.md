---
title: "Gewusst wie: Verwenden der ReadFile-Funktion von Windows (C#-Programmierhandbuch)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ReadFile-Funktion [C#]"
ms.assetid: 46bb53e0-a658-48c9-ae36-6720da7781c1
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "billchi"
manager: "douge"
---
# Gewusst wie: Verwenden der ReadFile-Funktion von Windows (C#-Programmierhandbuch)
In diesem Beispiel wird durch das Lesen und Anzeigen einer Textdatei die `ReadFile`\-Funktion von Windows veranschaulicht.  Für die `ReadFile`\-Funktion muss `unsafe`\-Code verwendet werden, da ein Zeiger als Parameter benötigt wird.  
  
 Das an die `Read`\-Funktion übergebene Bytearray ist ein verwalteter Typ.  Dies bedeutet, dass der Garbage Collector der Common Language Runtime \(CLR\) den vom Array belegten Speicher beliebig verschieben kann.  Um dies zu verhindern, wird mithilfe von [fixed](../Topic/fixed%20Statement%20\(C%23%20Reference\).md) ein Zeiger auf den Speicher abgerufen und gekennzeichnet, damit der Garbage Collector diesen nicht verschieben kann.  Am Ende des `fixed`\-Blocks wird der Speicher automatisch wieder in den Zustand zurückgesetzt, in dem er Verschiebungen durch die Garbage Collection unterliegt.  
  
 Diese Möglichkeit wird als *deklaratives Fixieren* bezeichnet.  Beim Fixieren ist der Verwaltungsaufwand sehr gering, sofern die Garbage Collection nicht im `fixed`\-Block auftritt. Dies ist jedoch nur sehr selten der Fall.  Fixieren kann jedoch zu einigen unerwünschten Seiteneffekten beim Ausführen der globalen Garbage Collection führen.  Die Garbage Collector\-Fähigkeit zum Komprimieren von Speicher wird durch fixierte Puffer stark beeinträchtigt.  Aus diesem Grund sollte das Fixieren nach Möglichkeit vermieden werden.  
  
## Beispiel  
 [!CODE [csProgGuidePointers#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#2)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../Topic/C%23%20Programming%20Guide.md)   
 [C\#\-Referenz](../Topic/C%23%20Reference.md)   
 [Unsicherer Code und Zeiger](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md)   
 [Zeigertypen](../Topic/Pointer%20types%20\(C%23%20Programming%20Guide\).md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)