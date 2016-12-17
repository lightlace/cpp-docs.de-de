---
title: "Hinzuf&#252;gen einer ATL-Eigenschaftenseite"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Eigenschaftenseiten"
  - "Steuerelemente [ATL], Eigenschaftenseiten"
  - "Eigenschaftenseiten, Hinzufügen"
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer ATL-Eigenschaftenseite
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Damit dem Projekt eine ATL \(Active Template Library\)\-Eigenschaftenseite hinzugefügt werden kann, ist es erforderlich, dass das Projekt als ATL\-Anwendung oder als MFC\-Anwendung mit ATL\-Unterstützung erstellt wurde.  Sie können den [ATL\-Projekt\-Assistenten](../../atl/reference/atl-project-wizard.md) verwenden, um eine ATL\-Anwendung zu erstellen, oder der [MFC\-Anwendung ein ATL\-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL\-Unterstützung in eine MFC\-Anwendung zu implementieren.  
  
 Wenn Sie eine Eigenschaftenseite für ein Steuerelement hinzufügen, muss das Steuerelement die [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)\-Schnittstelle unterstützen.  Wenn Sie ein [ATL\-Steuerelement erstellen](../../atl/reference/adding-an-atl-control.md), indem Sie den [ATL\-Steuerelement\-Assistenten](../../atl/reference/atl-control-wizard.md) ausführen, befindet sich diese Schnittstelle standardmäßig in der Ableitungsliste der Steuerelementklasse.  
  
> [!NOTE]
>  Wenn [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) nicht in der Ableitungsliste der Steuerelementklasse enthalten ist, müssen Sie sie manuell hinzufügen.  
  
### So fügen Sie dem Projekt eine ATL\-Eigenschaftenseite hinzu  
  
1.  Klicken Sie entweder im **Projektmappen\-Explorer** oder in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Namen des Projekts, dem Sie die ATL\-Eigenschaftenseite hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü zunächst auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Bereich "Vorlagen" des Dialogfelds [Klasse hinzufügen](../../ide/add-class-dialog-box.md) zunächst auf **ATL COM\+ 1.0\-Komponente** und dann auf **Öffnen**, um den [ATL COM\+ 1.0 Komponenten\-Assistenten](../../atl/reference/atl-property-page-wizard.md) anzuzeigen.  
  
 Nachdem Sie eine Eigenschaftenseite für ein Steuerelement erstellt haben, müssen Sie den [PROP\_PAGE](../Topic/PROP_PAGE.md)\-Eintrag in der Eigenschaftenzuordnung des Steuerelements angeben.  
  
## Siehe auch  
 [Eigenschaftenseiten](../../atl/atl-com-property-pages.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Example: Implementing a Property Page](../../atl/example-implementing-a-property-page.md)