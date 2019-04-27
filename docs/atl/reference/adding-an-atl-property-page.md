---
title: Hinzufügen einer ATL-Eigenschaftenseite
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: c61f666865d3e1db4cdcf2dc6d3e07c2113a79c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249098"
---
# <a name="adding-an-atl-property-page"></a>Hinzufügen einer ATL-Eigenschaftenseite

Um eine Eigenschaftenseite für die Active Template Library (ATL) zu Ihrem Projekt hinzuzufügen, muss Ihr Projekt erstellt worden haben als eine ATL-Anwendung oder einer MFC-Anwendung, die ATL-Unterstützung enthält. Können Sie die [ATL-Projektassistenten](../../atl/reference/atl-project-wizard.md) ATL-Anwendungen zu erstellen oder [Hinzufügen eines ATL-Objekts zu der MFC-Anwendung](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.

Wenn Sie eine Eigenschaftenseite für ein Steuerelement hinzufügen, muss das Steuerelement unterstützen die [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) Schnittstelle. Diese Schnittstelle wird standardmäßig in der Ableitungsliste des Steuerelements Klasse an, wenn Sie [Erstellen eines ATL-Steuerelements](../../atl/reference/adding-an-atl-control.md) mithilfe der [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md).

> [!NOTE]
> Wenn eine Klasse keinen [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) in der Ableitungsliste, Sie müssen diese manuell hinzufügen.

## <a name="to-add-an-atl-property-page-to-your-project"></a>Eine ATL-Eigenschaftenseite zu Ihrem Projekt hinzufügen

1. In einem **Projektmappen-Explorer** oder [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code), mit der rechten Maustaste in des Namens des Projekts, dem Sie die ATL-Eigenschaftenseite hinzufügen möchten.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.

1. In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) Dialogfeld die **Vorlagen** Bereich, klicken Sie auf **ATL-Eigenschaftenseite** , und klicken Sie dann auf **öffnen** zum Anzeigen der [ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md).

Wenn Sie eine Eigenschaftenseite für ein Steuerelement erstellen, müssen Sie angeben der [PROP_PAGE](property-map-macros.md#prop_page) Eintrag in der eigenschaftenzuordnung für das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../../atl/atl-com-property-pages.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Anpassen von mit VSTU Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)
