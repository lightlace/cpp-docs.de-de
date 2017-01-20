---
title: "&quot;(&quot; wurde nicht erwartet."
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
  - "vbc32095"
  - "bc32095"
helpviewer_keywords: 
  - "BC32095"
ms.assetid: a47ad15a-2cfc-4d17-9012-27ba85b7d783
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;(&quot; wurde nicht erwartet.
"\(" wurde nicht erwartet. Arrays von nicht instanziierten generischen Typen sind nicht zulässig.  
  
 [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] kann nur Arrays eines bestimmten Datentyps kompilieren. Sie können keinen data\-type\-Parameter eines generischen Typs als Datentyp eines Arrays verwenden.  
  
 **Fehler\-ID:** BC32095  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie ein Array verwenden möchten, müssen Sie es als einen bestimmten Datentyp deklarieren. Sie können keinen data\-type\-Parameter verwenden.  
  
-   Wenn Sie eine Gruppe von Elementen des Datentyps für einen data\-type\-Parameter angeben möchten, müssen Sie anstelle eines Arrays eine Auflistung verwenden.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [NIB: Auflistungen in Visual Basic](assetId:///8b2b7845-2251-4573-8dd3-c9f9c0a66a21)   
 [Verwalten von Gruppen von Objekten in Visual Basic](assetId:///50be4910-4732-4d5f-a18a-055a162e9037)