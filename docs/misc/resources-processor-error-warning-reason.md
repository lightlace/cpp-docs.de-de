---
title: "Resources processor error/warning: &lt;reason&gt;"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.resx_generator_task"
ms.assetid: eb9a1bd0-7e63-4a2b-ad37-54f6e67d9b5a
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "mblome"
manager: "douge"
---
# Resources processor error/warning: &lt;reason&gt;
Wenn ein Tool während der Verarbeitung einer RESX\-Datei einen Fehler oder eine Warnung zurückgibt, wird eine Fehlermeldung oder eine Warnung angezeigt.  Während des Buildvorgangs wandelt das Projektsystem alle RESX\-Dateien in binäre Dateien um, die vom [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Ressourcen\-Manager erkannt werden.  Für diese Transformation werden prozessinterne Tools verwendet.  
  
 Eine solche Fehlermeldung oder Warnung ist meistens auf eine fehlerhafte RESX\-Datei zurückzuführen.  Eine RESX\-Datei kann beschädigt werden, wenn die Datei außerhalb von Visual Studio oder innerhalb von Visual Studio mit einem Texteditor bearbeitet wurde.  
  
 Diese Dateien werden in der Regel durch den Windows Forms\- und den Web Forms\-Designer verwaltet.  
  
### So beheben Sie diesen Fehler  
  
1.  Berichtigen Sie das Format der RESX\-Datei.  
  
     Wenn ein Fehler angezeigt wird, wurde keine binäre Datei generiert, d. h., der Buildprozess schlägt fehl.  Warnungen werden nur zur Information ausgegeben.  
  
## Siehe auch  
 [Resources in .Resx File Format](assetId:///0c476133-87e4-47e8-b0ef-4b88f4ef3dc5)