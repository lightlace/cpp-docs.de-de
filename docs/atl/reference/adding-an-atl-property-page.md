---
title: Hinzufügen einer ATL-Eigenschaftenseite
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: 81f793fbdc6d9dda567051b8c35a96f3d3f2f470
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524627"
---
# <a name="adding-an-atl-property-page"></a>Hinzufügen einer ATL-Eigenschaftenseite

> [!NOTE] 
> Der ATL-Eigenschaftenseiten-Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

Damit Sie eine ATL-Eigenschaftenseite (Active Template Library) zu Ihrem Projekt hinzufügen können, muss Ihr Projekt als ATL- oder MFC-Anwendung erstellt worden sein, die ATL-Unterstützung enthält. Sie können den [ATL-Projekt-Assistenten](../../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

Wenn Sie eine Eigenschaftenseite für ein Steuerelement hinzufügen, muss das Steuerelement die Schnittstelle [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) unterstützen. Standardmäßig befindet sich diese Schnittstelle in der Ableitungsliste Ihrer Steuerelementklasse, wenn Sie den [ATL-Steuerelement-Assistenten](../../atl/reference/atl-control-wizard.md) verwenden, um [ein ATL-Steuerelement](../../atl/reference/adding-an-atl-control.md) zu erstellen.

> [!NOTE]
> Wenn [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) nicht in der Ableitungsliste Ihrer Steuerelementklasse enthalten ist, müssen Sie diese Schnittstelle manuell hinzufügen.

## <a name="to-add-an-atl-property-page-to-your-project"></a>So fügen Sie eine ATL-Eigenschaftenseite zum Projekt hinzu

1. Klicken Sie entweder im **Projektmappen-Explorer** oder in der [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) mit der rechten Maustaste auf den Namen des Projekts, dem Sie die ATL-Eigenschaftenseite hinzufügen möchten.

1. Klicken Sie im Kontextmenü auf **Hinzufügen**, und klicken Sie danach auf **Klasse hinzufügen**.

1. Klicken Sie im Dialogfeld [Klasse hinzufügen](../../ide/add-class-dialog-box.md) im Bereich **Vorlagen** auf **ATL-Eigenschaftenseite**, und klicken Sie dann auf **Öffnen**, um den [ATL-Eigenschaftenseiten-Assistenten](../../atl/reference/atl-property-page-wizard.md) anzuzeigen.

Sobald Sie eine Eigenschaftenseite für ein Steuerelement erstellen, müssen Sie den Eintrag [PROP_PAGE](property-map-macros.md#prop_page) in der Eigenschaftenzuordnung für das Steuerelement angeben.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../../atl/atl-com-property-pages.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Anpassen von mit VSTU Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)
