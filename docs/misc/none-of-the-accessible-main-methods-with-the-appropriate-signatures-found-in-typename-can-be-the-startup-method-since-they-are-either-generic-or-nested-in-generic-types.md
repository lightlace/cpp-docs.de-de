---
title: "Keine der in &#39;&lt;Typname&gt;&#39; gefundenen Main-Methoden mit den geeigneten Signaturen, auf die der Zugriff m&#246;glich ist, kann als Startmethode verwendet werden, da sie entweder generisch oder in generischen Typen geschachtelt sind."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30796"
  - "BC30796"
helpviewer_keywords: 
  - "BC30796"
ms.assetid: 606b3629-5a92-4c79-ace2-a530cab8c978
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "shoag"
manager: "wpickett"
---
# Keine der in &#39;&lt;Typname&gt;&#39; gefundenen Main-Methoden mit den geeigneten Signaturen, auf die der Zugriff m&#246;glich ist, kann als Startmethode verwendet werden, da sie entweder generisch oder in generischen Typen geschachtelt sind.
Eine Klasse, ein Modul oder eine Struktur weisen keine `Main`\-Prozedur auf, die sich als Projektstartprozedur qualifiziert.  
  
 Visual Basic erfordert, dass die Startprozedur für ein Projekt nicht von Typargumenten abhängig ist. Daher muss sie Zugriff auf mindestens eine `Main`\-Prozedur haben, die weder generisch noch in einem generischen Typ enthalten ist.  
  
 **Fehler\-ID:** BC30796  
  
### So beheben Sie diesen Fehler  
  
-   Definieren Sie mindestens eine der `Main`\-Prozeduren so, dass sie nicht generisch und nicht in einem generischen Typ enthalten ist.  
  
     \- oder \-  
  
-   Geben Sie auf der Seite **Eigenschaften** des Projekts ein anderes Formular oder Modul für das **Startformular** oder das **Startobjekt** an.  
  
## Siehe auch  
 [NIB: Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](assetId:///e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [NIB: Visual Basic\-Version von „Hello, World“](assetId:///9d030b60-e148-4366-a462-69532f02294c)