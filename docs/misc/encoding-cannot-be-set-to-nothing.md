---
title: "Die Codierung kann nicht auf &#39;Nothing&#39; festgelegt werden"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die Codierung kann nicht auf &#39;Nothing&#39; festgelegt werden
Fehler bei einem Lese\- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.  
  
 <xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll.  Der Standardwert ist UTF\-8.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie einen gültigen Wert für den `encoding`\-Parameter an.  
  
## Siehe auch  
 [File Encodings](../Topic/File%20Encodings%20\(Visual%20Basic\).md)   
 [Reading from Files](../Topic/Reading%20from%20Files%20in%20Visual%20Basic.md)   
 [Writing to Files](../Topic/Writing%20to%20Files%20in%20Visual%20Basic.md)   
 [My.Computer.FileSystem.ReadAllText\-Methode](assetId:///3a7ac8be-fb1d-4087-bc65-167d6754d57f)   
 [My.Computer.FileSystem.WriteAllText\-Methode](assetId:///f507460c-87d9-4504-b74f-3ff825c7d5c4)