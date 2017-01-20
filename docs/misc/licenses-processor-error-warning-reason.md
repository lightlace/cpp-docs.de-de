---
title: "Licenses processor error/warning: &lt;reason&gt;"
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
  - "vs.tasklisterror.licx_generator_task"
ms.assetid: 85750198-7bd3-4936-b1eb-954dcc3ff573
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# Licenses processor error/warning: &lt;reason&gt;
Wenn ein Tool während der Verarbeitung einer LICX\-Datei einen Fehler oder eine Warnung zurückgibt, wird eine Fehlermeldung oder eine Warnung angezeigt.  Während des Buildvorgangs wandelt das Projektsystem die Datei Licenses.licx \(sofern vorhanden\) in eine binäre Datei um, die vom [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Lizenz\-Manager erkannt wird.  Für diese Transformation werden prozessinterne Tools verwendet.  
  
 Eine solche Fehlermeldung oder Warnung ist meistens auf eine fehlerhafte LICX\-Datei zurückzuführen.  Eine LICX\-Datei kann beschädigt sein, wenn die Datei außerhalb von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] oder innerhalb von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] mit einem Text\-Editor bearbeitet wurde.  
  
 Diese Dateien werden in der Regel durch den Windows Forms\- und den Web Forms\-Designer verwaltet.  
  
### So beheben Sie diesen Fehler  
  
1.  Berichtigen Sie das Format der LICX\-Datei.  
  
     Wenn ein Fehler angezeigt wird, wurde keine binäre Datei generiert, d. h., der Buildprozess schlägt fehl.  Warnungen werden nur zur Information ausgegeben.  
  
## Siehe auch  
 [File Types and File Extensions in Visual Basic and Visual C\#](assetId:///f793852c-da06-4d52-a826-65f635844772)