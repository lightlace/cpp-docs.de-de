---
title: "Der &lt;typ&gt; &#39;&lt;typname&gt;&#39; f&#252;hrt Shadowing f&#252;r eine &#252;berschreibbare Methode in der Basisklasse aus"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc40005"
  - "bc40005"
helpviewer_keywords: 
  - "BC40005"
ms.assetid: 1dadda7f-1d26-4ae8-a668-9f69d55ceb50
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# Der &lt;typ&gt; &#39;&lt;typname&gt;&#39; f&#252;hrt Shadowing f&#252;r eine &#252;berschreibbare Methode in der Basisklasse aus
Der \<typ\> '\<typname\>' führt Shadowing für eine überschreibbare Methode in der Basisklasse aus. Wenn Sie die Basismethode überschreiben möchten, muss die Methode als 'Overrides' deklariert sein.  
  
 Ein Programmierelement wird mit demselben Namen wie eine überschreibbare Prozedur oder Eigenschaft deklariert, die in der Basisklasse definiert ist. In diesem Fall muss das Element in dieser Klasse Shadowing für das Element der Basisklasse ausführen.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC40005  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie die Basisprozedur überschreiben möchten, fügen Sie das Schlüsselwort `Overrides` zur Deklaration hinzu.  
  
-   Wenn Sie Shadowing für die Basisprozedur ausführen möchten, fügen Sie der Deklaration des Schlüsselwort `Shadows` hinzu.  
  
-   Wenn Sie weder Überschreiben noch Shadowing ausführen möchten, ändern Sie den Namen des deklarierten Elements.  
  
## Siehe auch  
 [NICHT IM BUILD: Überschreiben von Eigenschaften und Methoden](assetId:///2167e8f5-1225-4b13-9ebd-02591ba90213)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)   
 [Overrides](../Topic/Overrides%20\(Visual%20Basic\).md)   
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)