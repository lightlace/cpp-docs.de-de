---
title: "MSBuild Error MSB3142"
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
  - "MSBuild.GenerateBootstrapper.CopyError"
helpviewer_keywords: 
  - "MSB3142"
ms.assetid: acca7437-6c72-446c-a6b5-a1c051b6855f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3142
**MSB3142: Fehler beim Kopieren von \<Datei\> in \<Ordner\>': '\<Fehler\>'**  
  
 Dieser Fehler wird beim Kopieren von setup.bin in das Buildausgabeverzeichnis generiert.  Dieser Fehler kann folgende Ursachen haben:  
  
-   Sie verfügen nicht über die Berechtigung zum Kopieren in das Ausgabeverzeichnis.  
  
-   Der Datenträger ist voll.  
  
 Aus den gleichen Gründe kann auch file.copy oder directory.createdirectory scheitern.  
  
## Siehe auch  
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)