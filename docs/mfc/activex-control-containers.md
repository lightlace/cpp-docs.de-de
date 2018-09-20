---
title: ActiveX-Steuerelementcontainer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53598e416212cc042a2c53e964edcdf610dab654
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420633"
---
# <a name="activex-control-containers"></a>ActiveX-Steuerelementcontainer

Ein ActiveX-Steuerelementcontainer ist ein Container, der ActiveX-Steuerelemente vollständig unterstützt und kann diese in eigenen Windows oder Dialogfelder integrieren. Ein ActiveX-Steuerelement ist ein wiederverwendbarer Software-Element, das Sie in vielen Entwicklungsprojekten verwenden können. Steuerelemente können Benutzer Ihre Anwendung auf Datenbanken zugreifen, Daten zu überwachen und verschiedene Optionen in Ihren Anwendungen. Weitere Informationen zu ActiveX-Steuerelementen finden Sie im Artikel [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md).

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Control-Container werden in der Regel zwei Formen annehmen, in einem Projekt:

- Dialogfelder und Fenster der Dialogfeld-ähnliche wie z. B. Formularansichten, in denen ein ActiveX-Steuerelement an einer beliebigen Stelle im Dialogfeld verwendet wird.

- Windows in einer Anwendung, in denen ein ActiveX-Steuerelement in einer Symbolleiste oder einer anderen Stelle im Benutzerfenster verwendet wird.

Der ActiveX-Steuerelementcontainer mit dem Steuerelement über interagiert verfügbar gemachten [Methoden](../mfc/mfc-activex-controls-methods.md) und [Eigenschaften](../mfc/mfc-activex-controls-properties.md). Diese Methoden und Eigenschaften, die werden und können geändert werden, von dem Steuerelementcontainer, über eine Wrapperklasse, die in das ActiveX-Steuerelement-Container-Projekt zugegriffen werden. Das eingebettete ActiveX-Steuerelement kann auch mit dem Container interagieren, indem Sie das Auslösen von (senden) [Ereignisse](../mfc/mfc-activex-controls-events.md) um den Container zu informieren, die eine Aktion durchgeführt wurde. Der Steuerelement-Container können auf diese Benachrichtigungen die oder nicht reagiert.

Artikel beschreiben die verschiedenen Themen über das Erstellen eines ActiveX-Steuerelement-Container-Projekts für grundlegende Implementierungsprobleme im Zusammenhang mit ActiveX-Steuerelementcontainer, die mit Visual C++ erstellter:

- [Erstellen eines MFC-ActiveX-Steuerelementcontainers](../mfc/reference/creating-an-mfc-activex-control-container.md)

- [Container für ActiveX-Steuerelemente](../mfc/containers-for-activex-controls.md)

- [ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)

- [ActiveX-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer-Anwendung](../mfc/inserting-a-control-into-a-control-container-application.md)

- [ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)

- [ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-steuern](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)

- [ActiveX-Steuerelementcontainer: Anzeigen und Ändern von Steuerelementeigenschaften](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)

- [ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer](../mfc/programming-activex-controls-in-a-activex-control-container.md)

- [ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)

Weitere Informationen zur Verwendung von ActiveX-Steuerelemente in einem Dialogfeld finden Sie unter den [Dialog-Editor](../windows/dialog-editor.md) Themen.

Eine Liste von Artikeln, die die Details der Entwicklung von ActiveX-Steuerelemente, die mit Visual C++ und MFC-ActiveX-Steuerelementklassen beschreiben, finden Sie unter [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md). Die Artikel sind nach funktionale Kategorien gruppiert.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

