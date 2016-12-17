---
title: "Projektbuildwarnung PRJ0049"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0049"
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildwarnung PRJ0049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Relevante '\<Zielbezugnahme\>' erfordert .NET \<Framework MinFrameworkVersion\> und auf das Zielframework des Projekts nicht ausgeführt werden können  
  
 In Anwendungen, die mit [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] erstellt wurden, kann angegeben werden, welche [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Version ihr Ziel sein soll.  Wenn Sie einen Verweis auf eine Assembly oder ein Projekt hinzufügen, die bzw. das von einer [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Version abhängt, die älter ist als die Zielversion, erhalten Sie diese Warnung bei der Kompilierung.  
  
### So korrigieren Sie diese Warnung  
  
1.  Wählen Sie eine der folgenden Optionen aus:  
  
    -   Ändern Sie im Dialogfeld **Eigenschaftenseiten** des Projekts das Zielframework, sodass es aktueller ist als die Framework\-Mindestversion aller Assemblys und Projekte, auf die verwiesen wird, oder dieser Version entspricht.  Weitere Informationen finden Sie unter [Hinzufügen von Verweisen](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Entfernen Sie den Verweis auf die Assembly oder das Projekt mit einer Framework\-Mindestversion, die aktueller ist als das Zielframework.  Diese Elemente werden in den **Eigenschaftenseiten** des Projekts mit einem Warnsymbol markiert.  
  
## Siehe auch  
 [Projektbuildfehler und \-warnungen \(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)