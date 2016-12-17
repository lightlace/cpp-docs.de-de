---
title: "MSBuild Error MSB3127"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationDefaultIconNotInstalled"
helpviewer_keywords: 
  - "MSB3127"
ms.assetid: 161eea9a-332f-463e-a49e-d4030e937d52
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3127
**MSB3127: Das Standardsymbol \<Symbolname\> wurde in den aktuellen Dateiverweisen nicht gefunden oder ist nicht Bestandteil der erforderlichen Downloadgruppe.  Der Standardsymboldateiname beachtet die Groß\-\/Kleinschreibung, sodass der Dateiname, auf den im Anwendungsmanifest verwiesen wird, exakt mit dem Dateinamen des Symbols übereinstimmen muss.**  
  
 Wenn Sie eine Anwendung publizieren, die für die Verwendung von Dateizuordnungen konfiguriert ist, muss sich das Standardsymbol, auf das im Manifest verwiesen wird, in den aktuellen Dateiverweisen befinden oder Bestandteil der erforderlichen Downloadgruppe sein.  Das Standardsymbol ist das Symbol, das für Dateien angezeigt wird, bei denen die Dateizuordnung konfiguriert ist \(die konfigurierte Dateinamenerweiterung\).  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie die Symboldatei dem aktuellen Projekt hinzu, und nehmen Sie sie in die erforderliche Downloadgruppe auf.  Weitere Informationen finden Sie unter [How to: Specify Which Files Are Published by ClickOnce](../Topic/How%20to:%20Specify%20Which%20Files%20Are%20Published%20by%20ClickOnce.md).  
  
## Siehe auch  
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)