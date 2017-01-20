---
title: "MSBuild Error MSB3148"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.NoOutputPath"
helpviewer_keywords: 
  - "MSB3148"
ms.assetid: 389b335f-5760-4dcc-9146-c52d6d7ac81f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3148
**MSB3148: In den Buildeinstellungen wurde kein Ausgabepfad festgelegt.**  
  
 Dieser Fehler tritt auf, wenn der Ausgabepfad NULL oder ungültig ist, d. h., wenn in der Projektdatei beispielsweise `OutputPath=""` angegeben ist.  Der Standardwert für den Ausgabepfad ist `CurrentDirectory`.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass `OutputPath` in der Projektdatei enthalten und nicht leer ist.  
  
## Siehe auch  
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)