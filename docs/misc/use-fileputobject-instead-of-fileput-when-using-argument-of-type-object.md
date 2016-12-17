---
title: "Verwenden Sie FilePutObject statt FilePut, wenn ein Argument des Typs &quot;Object&quot; verwendet wird."
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
  - "vbrUseFilePutObject"
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Verwenden Sie FilePutObject statt FilePut, wenn ein Argument des Typs &quot;Object&quot; verwendet wird.
Die `FilePut`\-Methode enthält ein Argument des Typs`Object`.`FilePutObject` sollte anstelle von `FilePut` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
### So beheben Sie diesen Fehler  
  
-   Ersetzen Sie `FilePut` durch `FilePutObject`.  
  
-   Wandeln Sie das `Object`\-Argument in einen spezifischeren Typ um.  
  
-   Verwenden Sie die im `My.Computer.FileSystem`\-Objekt verfügbare Funktionalität.  
  
## Siehe auch  
 [NICHT IM BUILD: FilePutObject\-Funktion](assetId:///a0f52a1c-5ecc-4945-b18c-03147af61d6b)   
 [My.Computer.FileSystem Object](../Topic/My.Computer.FileSystem%20Object.md)   
 [My.Computer.FileSystem.WriteAllBytes\-Methode](assetId:///b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)