---
title: Hinzufügen einer ATL-Eigenschaftenseite | Microsoft-Dokumentation
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
ms.openlocfilehash: dfb5ec444be55d7b595660f7777ae54e19143fd4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021615"
---
# <a name="adding-an-atl-property-page"></a>Hinzufügen einer ATL-Eigenschaftenseite

Um eine Eigenschaftenseite für die Active Template Library (ATL) zu Ihrem Projekt hinzuzufügen, muss Ihr Projekt erstellt worden haben als eine ATL-Anwendung oder einer MFC-Anwendung, die ATL-Unterstützung enthält. Können Sie die [ATL-Projektassistenten](../../atl/reference/atl-project-wizard.md) ATL-Anwendungen zu erstellen oder [Hinzufügen eines ATL-Objekts zu der MFC-Anwendung](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.

Wenn Sie eine Eigenschaftenseite für ein Steuerelement hinzufügen, muss das Steuerelement unterstützen die [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) Schnittstelle. Diese Schnittstelle wird standardmäßig in der Ableitungsliste des Steuerelements Klasse an, wenn Sie [Erstellen eines ATL-Steuerelements](../../atl/reference/adding-an-atl-control.md) mithilfe der [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md).

> [!NOTE]
>  Wenn eine Klasse keinen [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) in der Ableitungsliste, Sie müssen diese manuell hinzufügen.

### <a name="to-add-an-atl-property-page-to-your-project"></a>Eine ATL-Eigenschaftenseite zu Ihrem Projekt hinzufügen

1. In einem **Projektmappen-Explorer** oder [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code), mit der rechten Maustaste in des Namens des Projekts, dem Sie die ATL-Eigenschaftenseite hinzufügen möchten.

2. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.

3. In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) klicken Sie im Dialogfeld im Vorlagenbereich die **ATL-Eigenschaftenseite** , und klicken Sie dann auf **öffnen** zum Anzeigen der [ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md).

Wenn Sie eine Eigenschaftenseite für ein Steuerelement erstellen, müssen Sie angeben der [PROP_PAGE](property-map-macros.md#prop_page) Eintrag in der eigenschaftenzuordnung für das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../../atl/atl-com-property-pages.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Beispiel: Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)

