---
title: "Hinzuf&#252;gen von Objekten und Steuerelementen zu einem ATL-Projekt"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Steuerelement-Assistent"
  - "ATL-Projekte, Hinzufügen von Steuerelementen"
  - "ATL-Projekte, Hinzufügen von Objekten"
  - "Steuerelemente [ATL], Hinzufügen zu Projekten"
  - "Objekte [C++], Hinzufügen zu ATL-Projekten"
  - "Assistenten [C++], ATL-Projekte"
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen von Objekten und Steuerelementen zu einem ATL-Projekt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können ATL\- oder MFC\-basierten Projekten ein Objekt oder ein Steuerelement hinzufügen, indem Sie einen der ATL\-Code\-Assistenten ausführen.  Für jedes hinzugefügte COM\-Objekt oder \-Steuerelement erstellt der Assistent CPP\- und H\-Dateien sowie eine RGS\-Datei für die skriptbasierte Registrierungsunterstützung.  Die folgenden ATL\-Code\-Assistenten sind in Visual Studio verfügbar:  
  
||||  
|-|-|-|  
|[ATL\-Assistent für einfache Objekte](../../atl/reference/atl-simple-object-wizard.md)|[ATL\-Dialogfeld\-Assistent](../../atl/reference/atl-dialog-wizard.md)|[ATL\-Steuerelement](../../atl/reference/atl-control-wizard.md)|  
|[ATL\-Eigenschaftenseite](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page\-Komponente](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL\-OLE DB\-Consumer\-Assistent](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[Assistent "ATL\-Unterstützung zu MFC hinzufügen"](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM\+ 1.0 Komponenten\-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL\-OLE DB\-Anbieter\-Assistent](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  Bevor Sie einem Projekt ein ATL\-Objekt hinzufügen, sollten Sie die objektspezifischen Details und Anforderungen in den betreffenden Hilfethemen nachschlagen.  
  
### So fügen Sie ein Objekt oder ein Steuerelement mit dem ATL\-Steuerelement\-Assistenten hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten, und klicken Sie im Kontextmenü auf **Hinzufügen**.  Klicken Sie auf **Klasse hinzufügen**.  
  
     Das Dialogfeld [Klasse hinzufügen](../../ide/add-class-dialog-box.md) wird angezeigt.  
  
2.  Während der ATL\-Ordner im Bereich **Kategorien** markiert ist, wählen Sie ein Objekt aus, das aus dem Bereich **Vorlagen** eingefügt werden soll.  Klicken Sie auf **Öffnen**.  Der Code\-Assistent für das ausgewählte Objekt wird angezeigt.  
  
    > [!NOTE]
    >  Wenn Sie einem MFC\-Projekt ein ATL\-Objekt hinzufügen möchten, müssen Sie dem vorhandenen Projekt ATL\-Unterstützung hinzufügen.  Befolgen Sie dazu beispielsweise die Hinweise unter [Hinzufügen von ATL\-Unterstützung zu einem MFC\-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
     Wenn Sie versuchen, Ihrem MFC\-Projekt ein ATL\-Objekt hinzuzufügen, ohne dass zuvor ATL\-Unterstützung hinzugefügt wurde, werden Sie von Visual Studio gefragt, ob Sie dem Projekt ATL\-Unterstützung hinzufügen möchten.  Klicken Sie auf **Ja**, um dem Projekt ATL\-Unterstützung hinzuzufügen und den ausgewählten ATL\-Assistenten zu öffnen.  
  
## Siehe auch  
 [ATL\-Projekt\-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+\-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmieren mit ATL\- und C\-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)