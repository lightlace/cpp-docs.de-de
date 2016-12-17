---
title: "Die Klasse &#39;&lt;Klassenname&gt;&#39; muss eine „Sub New“ deklarieren, da ihre Basisklasse &#39;&lt;Klassenname2&gt;&#39; keine zugreifbare „Sub New“ hat, die ohne Argumente aufgerufen werden kann."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30387"
  - "bc30387"
helpviewer_keywords: 
  - "BC30387"
ms.assetid: ff587e79-fa47-4b55-9a08-24688b209e0a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die Klasse &#39;&lt;Klassenname&gt;&#39; muss eine „Sub New“ deklarieren, da ihre Basisklasse &#39;&lt;Klassenname2&gt;&#39; keine zugreifbare „Sub New“ hat, die ohne Argumente aufgerufen werden kann.
Eine abgeleitete Klasse deklariert keinen Konstruktor, und [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] kann keinen Konstruktor generieren, da kein Basisklassenkonstruktor verfügbar ist, der aufgerufen werden kann.  
  
 Wenn eine abgeleitete Klasse keinen Konstruktor deklariert, versucht [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] einen impliziten parameterlosen Konstruktor zu generieren, der `MyBase.New()` aufruft. Wenn in der Basisklasse kein zugreifbarer Konstruktor vorhanden ist, der ohne Argumente aufgerufen werden kann \(bzw. wenn mehrere vorhanden sind\), kann [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] keinen impliziten Konstruktor generieren.  
  
 **Fehler\-ID:** BC30387  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren und implementieren Sie mindestens einen `Sub New`\-Konstruktor an einer beliebigen Stelle in der abgeleiteten Klasse.  
  
2.  Fügen Sie einen Aufruf eines Basisklassenkonstruktors `MyBase.New()` als erste Zeile jedes `Sub New` hinzu.  
  
## Siehe auch  
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: Verwenden von Konstruktoren und Destruktoren](assetId:///548eebe1-86c4-4377-b2f5-447cb8be3d90)   
 [Optional](../Topic/Optional%20\(Visual%20Basic\).md)   
 [ParamArray](../Topic/ParamArray%20\(Visual%20Basic\).md)   
 [Optional Parameters](../Topic/Optional%20Parameters%20\(Visual%20Basic\).md)   
 [Parameter Arrays](../Topic/Parameter%20Arrays%20\(Visual%20Basic\).md)