---
title: 'ActiveX-Steuerelementcontainer: Anzeigen und Ändern von Steuerelementeigenschaften | Microsoft Docs'
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
ms.openlocfilehash: ef443442cb19b9aaca82b74a0a5d8c72098d5cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340293"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX-Steuerelementcontainer: Anzeigen und Ändern von Steuerelementeigenschaften
Wenn Sie ein ActiveX-Steuerelement in ein Projekt einfügen, ist es hilfreich, anzeigen und Ändern der Eigenschaften, die vom ActiveX-Steuerelement unterstützt wird. In diesem Artikel erläutert, wie den Visual C++-Ressourcen-Editor zu diesem Zweck verwenden.  
  
 Wenn Ihre ActiveX-Steuerelementcontainer-Anwendung eingebettete Steuerelemente verwendet, können Sie anzeigen und ändern die Eigenschaften des Steuerelements im Ressourcen-Editor. Den Ressourcen-Editor können auch die Eigenschaftenwerte während der Entwurfszeit festlegen. Der Ressourcen-Editor speichert dann automatisch diese Werte in der Ressourcendatei für das Projekt. Jede Instanz des Steuerelements müssen dann die Eigenschaften, die mit diesen Werten initialisiert.  
  
 Dieses Verfahren setzt voraus, dass Sie das Projekt ein Steuerelement eingefügt. Informationen finden Sie unter [ActiveX-Steuerelementcontainer: Einfügen von einem Steuerelement in eine Steuerelementcontainer-Anwendung](../mfc/inserting-a-control-into-a-control-container-application.md).  
  
 Der erste Schritt bei der Anzeige von Eigenschaften des Steuerelements wird eine Instanz des Steuerelements für Dialogfeld-Projektvorlagen hinzugefügt.  
  
### <a name="to-view-the-properties-of-a-control"></a>Zum Anzeigen der Eigenschaften eines Steuerelements  
  
1.  Öffnen Sie in der Ressourcenansicht den **Dialogfeld** Ordner.  
  
2.  Öffnen Sie Ihre wichtigsten Dialogfeldvorlage.  
  
3.  Fügen Sie ein ActiveX-Steuerelement mithilfe der **ActiveX-Steuerelement einfügen** (Dialogfeld). Weitere Informationen finden Sie unter [anzeigen und Hinzufügen von ActiveX-Steuerelementen zu einem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
4.  Wählen Sie das ActiveX-Steuerelement im Dialogfeld ein.  
  
5.  Klicken Sie im Eigenschaftenfenster auf die **Eigenschaften** Schaltfläche.  
  
 Verwenden der **Eigenschaften** (Dialogfeld), ändern und neue Eigenschaften sofort zu testen.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

