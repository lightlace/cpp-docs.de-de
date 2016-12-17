---
title: "The project file &#39;&lt;filename&gt;&#39; cannot be updated"
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
  - "vs.UpgradeErrors"
ms.assetid: ecd1e161-c51c-4aaa-ab80-8fc443bdad81
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# The project file &#39;&lt;filename&gt;&#39; cannot be updated
Sie versuchen, ein Projekt zu öffnen, das in einer früheren Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] erstellt wurde.  Das Projekt muss auf das aktuelle Format aktualisiert werden, kann jedoch nicht aktualisert werden, weil die angegebene Projektdatei \(**.vbproj**\) entweder schreibgeschützt ist oder der Quellverwaltung unterliegt und gegenwärtig durch einen anderen Benutzer gesperrt wird.  
  
### So beheben Sie diesen Fehler  
  
1.  Im Datei\-Explorer suchen Sie die angegebene Projektdatei.  
  
2.  Klicken Sie im Menü **Datei** auf **Eigenschaften**.  
  
3.  Deaktivieren Sie im Dialogfeld **Eigenschaften** das Attribut **Schreibgeschützt**.  
  
 Wenn die Datei von der Quellcodeverwaltung gesteuert und durch einen anderen Benutzer gesperrt wird, warten Sie, bis sie verfügbar ist, und checken Sie sie lokal aus.  
  
## Siehe auch  
 [NIB: Project Properties \(Visual Studio\)](assetId:///eb4c97ed-f667-4850-98d0-6e2a4d21bbca)