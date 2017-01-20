---
title: "Projekttyp nicht verf&#252;gbar."
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
  - "vs.projecttypenotavailable"
helpviewer_keywords: 
  - "Projekttyp nicht verfügbar (Fehler)."
ms.assetid: a579fe75-efa2-4dd0-b5d7-ae106d3aedbd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# Projekttyp nicht verf&#252;gbar.
In diesem Dialogfeld wird folgende Fehlermeldung angezeigt: "Das Projekt \<Projekt\> kann nicht geöffnet werden, weil der Projekttyp \<Projekttyp\> von dieser Version der Anwendung nicht unterstützt wird."  
  
## Problemumgehung  
  
-   Dieses Dialogfeld wird angezeigt, da das zum Öffnen der angegebenen Datei erforderliche Produkt bzw. die erforderliche Produktversion nicht gefunden wurde.  Dieser Fehler tritt im Allgemeinen auf, wenn versucht wird, eine Projektdatei zu öffnen, die mit der installierten Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] nicht geöffnet werden kann.  Wenn Sie beispielsweise versuchen, eine [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\-Projektdatei mit [!INCLUDE[vbprvbxprlong](../misc/includes/vbprvbxprlong_md.md)] zu öffnen, wird dieses Dialogfeld angezeigt.  
  
#### So umgehen Sie diesen Fehler  
  
-   Installieren Sie die richtige Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Siehe auch  
 [Portieren, Migrieren und Aktualisieren von Visual Studio\-Projekten](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md)   
 [Projekteigenschaftenverweise](../Topic/Project%20Properties%20Reference.md)