---
title: Hinzufügen eines einfachen ATL-Objekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.adding.atl
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- objects [ATL]
- ATL, simple objects
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1347fcebc6a3793cbe63ae356f7f9d2e03742cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109768"
---
# <a name="adding-an-atl-simple-object"></a>Hinzufügen eines einfachen ATL-Objekts

Um ein Objekt der ATL (Active Template Library) zu Ihrem Projekt hinzuzufügen, muss Ihr Projekt erstellt worden haben als eine ATL-Anwendung oder einer MFC-Anwendung, die ATL-Unterstützung enthält. Sie können den [ATL-Projekt-Assistenten](../../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

Sie können COM-Schnittstellen für das neue ATL-Objekt definieren, wenn Sie erstmalig erstellen, oder später hinzufügen, indem Sie mit der [Schnittstelle implementieren](../../ide/implement-interface-wizard.md) Befehl im Kontextmenü "Klassenansicht".

### <a name="to-add-an-atl-simple-object-to-your-atl-com-project"></a>Ein einfaches ATL-Objekt das ATL-COM-Projekt hinzu

1. In einem **Projektmappen-Explorer** oder [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code), mit der rechten Maustaste in des Namens des Projekts, dem Sie die einfache ATL-Objekt hinzufügen möchten.

2. Klicken Sie im Kontextmenü auf die Option **Hinzufügen**, und klicken Sie danach auf **Klasse hinzufügen**.

3. In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) im Dialogfeld im Bereich "Vorlagen", klicken Sie auf **einfaches ATL-Objekt**, und klicken Sie dann auf **öffnen** zum Anzeigen der [einfachen ATL-Objektassistenten](../../atl/reference/atl-simple-object-wizard.md).

4. Legen Sie zusätzliche Optionen für Ihr Projekt auf die [Optionen](../../atl/reference/options-atl-simple-object-wizard.md) Seite des Assistenten für einfaches ATL-Objekt.

5. Klicken Sie auf **Fertig stellen** zum Hinzufügen des Objekts zu Ihrem Projekt.

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[Hinzufügen von Verbindungspunkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md)<br/>
[Hinzufügen einer Methode](../../ide/adding-a-method-visual-cpp.md)<br/>
[MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Hinzufügen einer generischen C++-Klasse](../../ide/adding-a-generic-cpp-class.md)

