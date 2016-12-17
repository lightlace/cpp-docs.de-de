---
title: "&lt;fehler&gt;: &#39;&lt;konstruktorname1&gt;&#39; ruft &#39;&lt;konstruktorname2&gt;&#39; auf"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30297"
  - "bc30297"
helpviewer_keywords: 
  - "BC30297"
ms.assetid: dfca67d7-f4d7-4451-a937-68f22b8527d5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;fehler&gt;: &#39;&lt;konstruktorname1&gt;&#39; ruft &#39;&lt;konstruktorname2&gt;&#39; auf
Es tritt ein zirkulärer Konstruktoraufruf auf. Ein Konstruktor nimmt einen Aufruf von `Me.New()` oder `MyClass.New()` vor. Eine mögliche Ursache ist ein Versuch, einen überladenen Konstruktor mit einer anderen Argumentliste aufzurufen.  
  
 **Fehler\-ID:** BC30297  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie eine andere Argumentliste, um einen überladenen Konstruktor aufzurufen.  
  
-   Wenn keine Überladungen zugänglich sind, entfernen Sie den Aufruf von `Me.New()` oder `MyClass.New()`.  
  
## Siehe auch  
 [NICHT IM BUILD: Verwenden von Konstruktoren und Destruktoren](assetId:///548eebe1-86c4-4377-b2f5-447cb8be3d90)