---
title: Hinzufügen einer ATL-Eigenschaftenseite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c84cdabddb96d2deeecd09f26101e37d9c99d0ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-atl-property-page"></a>Hinzufügen einer ATL-Eigenschaftenseite
Um Ihrem Projekt eine Eigenschaftenseite für die Active Template Library (ATL) hinzugefügt haben, dass das Projekt als ATL-Anwendung oder als MFC-Anwendung, die ATL-Unterstützung enthält erstellt wurde. Können Sie die [ATL-Projektassistenten](../../atl/reference/atl-project-wizard.md) eine ATL-Anwendung erstellen oder [Hinzufügen eines ATL-Objekts zu der MFC-Anwendung](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.  
  
 Wenn Sie eine Eigenschaftenseite für ein Steuerelement hinzufügen, muss das Steuerelement unterstützen die [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) Schnittstelle. Standardmäßig ist diese Schnittstelle in der Ableitungsliste des Steuerelements Klasse an, wenn Sie [erstellen ein ATL-Steuerelements](../../atl/reference/adding-an-atl-control.md) mithilfe der [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Wenn die Steuerelementklasse keinen [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) in der Ableitungsliste, Sie müssen diese manuell hinzufügen.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>So fügen Sie eine ATL-Eigenschaftenseite zu Ihrem Projekt hinzu  
  
1.  In beiden **Projektmappen-Explorer** oder [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste in des Namens des Projekts, dem Sie die ATL-Eigenschaftenseite hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.  
  
3.  In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) (Dialogfeld), klicken Sie im Bereich "Vorlagen" klicken Sie auf **ATL-Eigenschaftenseite** , und klicken Sie dann auf **öffnen** zum Anzeigen der [ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md).  
  
 Nachdem Sie eine Eigenschaftenseite für ein Steuerelement erstellt haben, geben Sie die [PROP_PAGE](property-map-macros.md#prop_page) Eintrag in der eigenschaftenzuordnung für das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../../atl/atl-com-property-pages.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Beispiel: Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)

