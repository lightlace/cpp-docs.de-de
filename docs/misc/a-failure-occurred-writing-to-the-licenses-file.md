---
title: "A failure occurred writing to the licenses file"
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
  - "vs.tasklisterror.fail_writing_licenses_file"
ms.assetid: 7ea1e2ac-fc94-4d53-8ce9-2ae31bcba85d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# A failure occurred writing to the licenses file
Das Projektsystem konnte nicht in die umgewandelte Datei schreiben.  Bei der Lizenzvorbereitung wandelt das Projektsystem LICX\-Textdateien in binäre Lizenzdateien um, die vom [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Lizenzierungssystem gelesen werden können.  
  
 Dieser Fehler kann z. B. durch fehlende Speicherkapazität auf dem Gerät oder durch die Überschreitung der zulässigen **MAX\_PATH**\-Begrenzung für Dateinamen verursacht werden.  
  
 **So beheben Sie diesen Fehler**  
  
-   Verschieben Sie das Projekt in einen anderen Ordner mit einem kurzen absoluten Pfadnamen, oder kürzen Sie den Ausgabedateinamen.  
  
     Der Buildprozess schlägt fehl, wenn dieser Fehler auftritt.  
  
## Siehe auch  
 [How to: License Components and Controls](../Topic/How%20to:%20License%20Components%20and%20Controls.md)