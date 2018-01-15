---
title: ActiveX-Steuerelementcontainer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee24d39c8769eaf2216ca4f64b9856b778a51ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers"></a>ActiveX-Steuerelementcontainer
Ein ActiveX-Steuerelementcontainer ist ein Container, der vollständig ActiveX-Steuerelemente unterstützt und kann in einem eigenen Fenster und Dialogfelder integrieren. Ein ActiveX-Steuerelement ist eine wiederverwendbare Softwarekomponente, die Sie in vielen Entwicklungsprojekte verwenden können. Steuerelemente können Ihre Anwendung Benutzer Zugriff auf Datenbanken, überwacht werden, und stellen verschiedene Auswahlen in Ihre Anwendungen. Weitere Informationen zu ActiveX-Steuerelemente, finden Sie im Artikel [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md).  
  
 Steuerelementcontainer nehmen zwei Formen in der Regel in einem Projekt:  
  
-   Dialogfeldern und Fenstern der Dialogfeld-ähnliche z. B. Formularansichten, bei denen ein ActiveX-Steuerelement an einer beliebigen Stelle im Dialogfeld dient.  
  
-   Windows in einer Anwendung, in denen ein ActiveX-Steuerelement in einer Symbolleiste oder einer anderen Position im Benutzerfenster verwendet wird.  
  
 Die ActiveX-Steuerelementcontainer mit dem Steuerelement über interagiert verfügbar gemachte [Methoden](../mfc/mfc-activex-controls-methods.md) und [Eigenschaften](../mfc/mfc-activex-controls-properties.md). Der Zugriff auf diese Methoden und Eigenschaften, die Zugriff auf und geändert werden können von dem Steuerelementcontainer, erfolgt über eine Wrapperklasse, die in der ActiveX-Steuerelementcontainer-Projekt. Das eingebettete ActiveX-Steuerelement kann auch mit dem Container durch Auslösen (senden) interagieren [Ereignisse](../mfc/mfc-activex-controls-events.md) auf den Container zu informieren, die eine Aktion aufgetreten ist. Der Steuerelementcontainer können diese Benachrichtigungen oder nicht reagieren.  
  
 Zusätzliche Artikel werden verschiedene Themen, erstellen Sie ein ActiveX-Steuerelementcontainer-Projekt für grundlegende Implementierung Probleme im Zusammenhang mit ActiveX-Steuerelementcontainer mit Visual C++ erstellten behandelt:  
  
-   [Erstellen eines MFC-ActiveX-Steuerelementcontainers](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [Container für ActiveX-Steuerelemente](../mfc/containers-for-activex-controls.md)  
  
-   [ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [ActiveX-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer-Anwendung](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-steuern](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX-Steuerelementcontainer: Anzeigen und Ändern von Steuerelementeigenschaften](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Weitere Informationen zum Verwenden von ActiveX-Steuerelemente in einem Dialogfeld finden Sie unter der [Dialog-Editor](../windows/dialog-editor.md) Themen.  
  
 Eine Liste von Artikeln, die die Details der Entwicklung von ActiveX-Steuerelemente, die mit Visual C++ und MFC-ActiveX-Steuerelementklassen erläutern, finden Sie unter [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md). Die Artikel werden durch funktionale Kategorien gruppiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

