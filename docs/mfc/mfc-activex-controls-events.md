---
title: 'MFC-ActiveX-Steuerelemente: Ereignisse'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
ms.openlocfilehash: 0d8a881d07a3e48673c6dc3298816d165273be0d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276766"
---
# <a name="mfc-activex-controls-events"></a>MFC-ActiveX-Steuerelemente: Ereignisse

ActiveX-Steuerelemente verwenden Ereignisse, um einen Container zu informieren, den auf das Steuerelement der etwas passiert ist. Gängige Beispiele für Ereignisse enthalten, auf das Steuerelement Daten eingegeben haben, verwenden die Tastatur, und Änderungen in den Zustand des Steuerelements klickt. Wenn diese Aktionen auftreten, löst das Steuerelement eine Ereignis, um den Container zu benachrichtigen.

Ereignisse werden auch Nachrichten bezeichnet.

MFC unterstützt zwei Arten von Ereignissen: vordefinierte und benutzerdefinierte. Vordefinierte Ereignisse sind die Ereignisse, die Klasse [COleControl](../mfc/reference/colecontrol-class.md) automatisch behandelt. Eine vollständige Liste der vordefinierten Ereignissen, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Benutzerdefinierte Ereignisse ermöglichen ein Steuerelement die Möglichkeit, den Container zu benachrichtigen, wenn eine Aktion, die speziell für dieses Steuerelement stattfindet. Einige Beispiele sind eine Änderung in den internen Zustand eines Steuerelements oder der Empfang einer Fensternachricht bestimmte.

Für das Steuerelement, Ereignisse ordnungsgemäß auszulösen muss die Steuerelementklasse jedes Ereignis des Steuerelements auf eine Memberfunktion zuordnen, die aufgerufen werden soll, wenn das zugehörige Ereignis eintritt. Dieser Zuordnungsmechanismus (eine Event-Zuordnung bezeichnet) zeigt Informationen über das Ereignis und durch die Visual Studio ganz einfach aufrufen und bearbeiten die Ereignisse des Steuerelements. Dieses Event-Zuordnung wird deklariert, indem folgendes Makro auf, befindet sich in der Kopfzeile (. H)-Datei von der Klassendeklaration des Steuerelements:

[!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]

Nachdem die ereigniszuordnung deklariert wurde, muss er im Ihres Steuerelements-Implementierung definiert werden (. CPP)-Datei. Die folgenden Codezeilen definieren die ereigniszuordnung, die Ihrer Kontrolle bestimmter Ereignisse ausgelöst werden können:

[!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

Wenn Sie die MFC-ActiveX-Steuerelement-Assistent zum Erstellen des Projekts verwenden, fügt es automatisch diese Zeilen hinzu. Wenn Sie nicht die MFC-ActiveX-Steuerelement-Assistenten verwenden, müssen Sie diese Zeilen auch manuell hinzufügen.

In der Klassenansicht, können Sie vordefinierte Ereignisse, die von der Klasse unterstützt hinzufügen `COleControl` oder benutzerdefinierte Ereignisse, die Sie definieren. Für jedes neue Ereignis hinzugefügt Klassenansicht automatisch den ordnungsgemäßen Eintrag des Steuerelements Event-Zuordnung und des Steuerelements. IDL-Datei.

Zwei weitere Artikel behandeln Ereignisse im Detail:

- [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen](../mfc/mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl-Klasse](../mfc/reference/colecontrol-class.md)
