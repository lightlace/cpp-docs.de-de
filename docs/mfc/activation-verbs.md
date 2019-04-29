---
title: 'Aktivierung: Verbs'
ms.date: 11/04/2016
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
ms.openlocfilehash: baf8e0ac3527407b2e5ba77dfdf3921419217fd7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392907"
---
# <a name="activation-verbs"></a>Aktivierung: Verbs

In diesem Artikel wird erläutert, die primären und sekundären Verben Rollenspiele in OLE [Aktivierung](../mfc/activation-cpp.md).

In der Regel durch Doppelklicken auf ein eingebettetes Element, wird die Benutzer zu bearbeiten kann. Allerdings sind bestimmte Elemente nicht auf diese Weise Verhalten. Beispielsweise wird durch Doppelklicken auf ein Element mit der Audiorecorder-Anwendung erstellt nicht die Server in einem separaten Fenster geöffnet; Stattdessen gibt den Sound wieder.

Der Grund für diesen Unterschied Verhalten ist, dass Audiorecorder-Elementen ein anderes "primäres Verb." Primäre Verb ist die Aktion ausgeführt, wenn ein OLE-Element doppelgeklickt wird. Für die meisten Typen von OLE-Elementen ist das primäre Verb bearbeiten, der den Server gestartet wird, die das Element erstellt hat. Für einige Typen von Elementen wie Audiorecorder-Elementen ist das primäre Verb Play.

Viele Arten von OLE-Elementen unterstützt nur ein Verb, und bearbeiten ist die am häufigsten verwendeten. Einige Elementtypen unterstützen jedoch mehrere Verben. Audiorecorder Elemente unterstützen z. B. als sekundären Verb bearbeiten.

Eine andere häufig verwendete Verb ist "Open". Das Open-Verb ist identisch mit "Bearbeiten", außer die Serveranwendung in einem separaten Fenster gestartet wird. Dieses Verb sollte verwendet werden, wenn die containeranwendung oder die Serveranwendung die direkte Aktivierung nicht unterstützt.

Alle Verben außer das primäre Verb müssen über ein Untermenübefehl aufgerufen werden, wenn das Element ausgewählt ist. Dieses Untermenü enthält alle Verben, die vom Element unterstützt und wird normalerweise durch die *Typename* **Objekt** Befehl die **bearbeiten** Menü. Informationen zu den *Typename* **Objekt** Befehl, finden Sie im Artikel [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md).

Die Verben, die eine Server-Anwendung unterstützt werden in der Datenbank der Windows-Registrierung aufgeführt. Wenn die Server-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben ist, wird automatisch alle Verben registriert, wenn der Server gestartet wurde. Wenn dies nicht der Fall ist, sollten Sie diese während der Initialisierungsphase der Serveranwendung registrieren. Weitere Informationen finden Sie im Artikel [Registrierung](../mfc/registration.md).

## <a name="see-also"></a>Siehe auch

[Activation (Aktivierung)](../mfc/activation-cpp.md)<br/>
[Container](../mfc/containers.md)<br/>
[Server](../mfc/servers.md)
