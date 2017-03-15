---
title: "Specifying Property Pages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISpecifyPropertyPages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages method"
  - "Eigenschaftenseiten, Angeben"
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Specifying Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein ActiveX\-Steuerelement erstellen, sollten Sie es häufig mit Eigenschaftenseiten zuordnen, die verwendet werden können, um die Eigenschaften des Steuerelements festzulegen.  Steuerelementcontainer verwenden die **ISpecifyPropertyPages**\-Schnittstelle, um zu ermitteln, die Eigenschaftenseiten verwendet werden können, um die Eigenschaften des Steuerelements festzulegen.  Sie müssen diese Schnittstelle im Steuerelement implementieren.  
  
 Um **ISpecifyPropertyPages** mit ATL zu implementieren, müssen Sie die folgenden Schritte:  
  
1.  Leiten Sie die Klasse von [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).  
  
2.  Fügen Sie einen Eintrag für **ISpecifyPropertyPages** der COM\-Zuordnung der Klasse hinzu.  
  
3.  Fügen Sie einen Eintrag [PROP\_PAGE](../Topic/PROP_PAGE.md) der Eigenschaftenzuordnung für jede Seite hinzu, die dem Steuerelement zugeordnet ist.  
  
> [!NOTE]
>  Wenn Sie ein Standardsteuerelement mithilfe [ATL\-Steuerelement\-Assistent](../atl/reference/atl-control-wizard.md) generieren, müssen Sie nur die `PROP_PAGE` Einträge der Eigenschaftenzuordnung hinzufügen.  Der Assistent generiert den erforderlichen Code für die anderen Schritte.  
  
 Gut konzipierte Container zeigen die angegebenen Eigenschaftenseiten in derselben Reihenfolge, die die `PROP_PAGE` Einträge in der Eigenschaft zuordnen.  Im Allgemeinen sollten Sie Standardeigenschaftenseiteneinträge nachdem die Einträge für Ihre benutzerdefinierten Seiten in die Eigenschaftenzuordnung einfügen, sodass die Seiten finden, die dem Steuerelement zuerst spezifisch sind.  
  
## Beispiel  
 Die folgende Klasse für ein Kalendersteuerelement verwendet die **ISpecifyPropertyPages**\-Schnittstelle, um Containern mitzuteilen, dass seine Eigenschaften mit einer benutzerdefinierten Datumsseite und der vordefinierten Farbenseite festgelegt werden können.  
  
 [!CODE [NVC_ATL_Windowing#72](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#72)]  
  
## Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages\-Beispiel](../top/visual-cpp-samples.md)