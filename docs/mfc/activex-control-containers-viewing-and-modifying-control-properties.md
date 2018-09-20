---
title: 'ActiveX-Steuerelementcontainer: Anzeigen und Ändern von Steuerelementeigenschaften | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9614ecfcd23418f8b0abc08622e8c272bb5548a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388822"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX-Steuerelementcontainer: Anzeigen und Ändern von Steuerelementeigenschaften

Wenn Sie ein ActiveX-Steuerelement in ein Projekt einfügen, ist es hilfreich, anzeigen und Ändern der Eigenschaften, die vom ActiveX-Steuerelement unterstützt wird. In diesem Artikel wird erläutert, wie den Visual C++-Ressourcen-Editor zu diesem Zweck verwenden.

Wenn Ihr ActiveX-Steuerelementcontainer-Anwendung eingebettete Steuerelementen verwendet, können Sie anzeigen und ändern die Eigenschaften des Steuerelements im Ressourcen-Editor. Sie können auch den Ressourcen-Editor verwenden, können Sie während der Entwurfszeit festlegen. Der Ressourcen-Editor speichert dann automatisch diese Werte in Ressourcen-Datei des Projekts. Jede Instanz des Steuerelements müssen die Eigenschaften, die mit diesen Werten initialisiert.

Dieses Verfahren setzt voraus, dass Sie ein Steuerelement in Ihrem Projekt eingefügt haben. Weitere Informationen finden Sie unter [ActiveX-Steuerelementcontainer: Einfügen von einem Steuerelement in eine Steuerelementcontainer-Anwendung](../mfc/inserting-a-control-into-a-control-container-application.md).

Der erste Schritt beim Anzeigen der Eigenschaften des Steuerelements ist eine Instanz des Steuerelements Dialogfeldvorlage des Projekts hinzu.

### <a name="to-view-the-properties-of-a-control"></a>Anzeigen die Eigenschaften eines Steuerelements

1. Öffnen Sie in der Ressourcenansicht den **Dialogfeld** Ordner.

1. Öffnen Sie Ihre wichtigsten Dialogfeldvorlage.

1. Fügen Sie ein ActiveX-Steuerelement mit dem **ActiveX-Steuerelement einfügen** Dialogfeld. Weitere Informationen finden Sie unter [anzeigen und Hinzufügen von ActiveX-Steuerelementen in einem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

1. Wählen Sie das ActiveX-Steuerelement im Dialogfeld ein.

1. Klicken Sie im Eigenschaftenfenster auf die **Eigenschaften** Schaltfläche.

Verwenden der **Eigenschaften** Dialogfelds ändern und neue Eigenschaften sofort testen.

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

