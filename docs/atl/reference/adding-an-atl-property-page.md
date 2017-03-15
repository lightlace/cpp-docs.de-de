---
title: "Eine ATL-Eigenschaftenseite hinzufügen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 7b6a6220a33890d99e6fb2bd81ce832b38720c50
ms.lasthandoff: 02/24/2017

---
# <a name="adding-an-atl-property-page"></a>Hinzufügen einer ATL-Eigenschaftenseite
Um eine Eigenschaftenseite Active Template Library (ATL) zu Ihrem Projekt hinzuzufügen, dass Ihr Projekt als ATL-Anwendung oder einer MFC-Anwendung mit ATL-Unterstützung erstellt wurde. Können Sie die [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md) eine ATL-Anwendung erstellen oder [der MFC-Anwendung ein ATL-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.  
  
 Wenn Sie eine Eigenschaftenseite für ein Steuerelement hinzufügen, muss das Steuerelement unterstützt die [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) Schnittstelle. Diese Schnittstelle ist standardmäßig in der Ableitungsliste des Steuerelements Klasse, wenn Sie [erstellen ein ATL-Steuerelements](../../atl/reference/adding-an-atl-control.md) mithilfe der [ATL-Steuerelement-Assistenten](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Wenn eine Klasse keinen [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) in der Ableitungsliste, Sie müssen diese manuell hinzufügen.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>Um dem Projekt eine ATL-Eigenschaftenseite hinzufügen  
  
1.  In beiden **Projektmappen-Explorer** oder [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste des Namens des Projekts, dem Sie die ATL-Eigenschaftenseite hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen** und klicken Sie dann auf **Klasse hinzufügen**.  
  
3.  In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) klicken Sie im Dialogfeld im Bereich Vorlagen auf **ATL-Eigenschaftenseite** und klicken Sie dann auf **öffnen** zum Anzeigen der [ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md).  
  
 Wenn Sie eine Eigenschaftenseite für ein Steuerelement erstellen, geben Sie die [PROP_PAGE](http://msdn.microsoft.com/library/2155973e-b96c-4385-bf85-5d6112c969b8) Eintrag in der eigenschaftszuordnung für das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../../atl/atl-com-property-pages.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Beispiel: Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)


