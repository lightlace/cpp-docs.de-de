---
title: "Unzul&#228;ssige Verwendung des Schl&#252;sselworts &lt;Schl&#252;sselwort&gt; in einem Modul"
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
  - "vbc42028"
  - "BC42028"
helpviewer_keywords: 
  - "BC42028"
ms.assetid: a9bc1e9d-ba2c-4a71-b147-0fb66f670316
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "shoag"
manager: "wpickett"
---
# Unzul&#228;ssige Verwendung des Schl&#252;sselworts &lt;Schl&#252;sselwort&gt; in einem Modul
Module verfügen nicht über Instanzen, unterstützen keine Vererbung und implementieren keine Schnittstellen. Daher gelten die folgenden Schlüsselwörter nicht für eine Moduldeklaration:  
  
-   [MustInherit](../Topic/MustInherit%20\(Visual%20Basic\).md)  
  
-   [NotInheritable](../Topic/NotInheritable%20\(Visual%20Basic\).md)  
  
-   [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)  
  
-   [Private](../Topic/Private%20\(Visual%20Basic\).md)  
  
-   [Protected](../Topic/Protected%20\(Visual%20Basic\).md)  
  
-   [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)  
  
-   [Shared](../Topic/Shared%20\(Visual%20Basic\).md)  
  
-   [Static](../Topic/Static%20\(Visual%20Basic\).md)  
  
 Die einzigen Schlüsselwörter, die in einer [Module Statement](../Topic/Module%20Statement.md) unterstützt werden, sind [Public](../Topic/Public%20\(Visual%20Basic\).md) und [Friend](../Topic/Friend%20\(Visual%20Basic\).md).  
  
 Darüber hinaus können Sie die [Implements](../Topic/Implements%20Clause%20\(Visual%20Basic\).md)\-Anweisung oder die [Inherits Statement](../Topic/Inherits%20Statement.md) im Anweisungsblock des Moduls nicht verwenden.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC42028  
  
### So beheben Sie diesen Fehler  
  
-   Wenn dieses Programmierelement ein Modul sein soll, verwenden Sie nur das `Public`\- oder `Friend`\-Schlüsselwort in der Deklaration. Standardmäßig verwendet ein Modul `Friend`, wenn Sie keine Zugriffsebene angeben.  
  
-   Wenn Sie Instanzen dieses Programmierelements erstellen möchten, deklarieren Sie es als Klasse. Sie können dann die Schlüsselwörter verwenden, die für eine Klassendeklaration gelten.  
  
## Siehe auch  
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)