---
title: 'MFC-ActiveX-Steuerelemente: Ereignisse | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6c8ee059b4136ce1504117246abd12ac74a6233
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348389"
---
# <a name="mfc-activex-controls-events"></a>MFC-ActiveX-Steuerelemente: Ereignisse
ActiveX-Steuerelemente verwenden Ereignisse, um einen Container zu informieren, den an das Steuerelement dem ein Fehler aufgetreten ist. Typische Beispiele für Ereignisse sind auf das Steuerelement, Daten mithilfe der Tastatur und die Änderungen in den Zustand des Steuerelements klickt. Wenn diese Aktionen auftreten, löst das Steuerelement eine Ereignis, um den Container zu benachrichtigen.  
  
 Ereignisse werden auch Nachrichten bezeichnet.  
  
 MFC unterstützt zwei Arten von Ereignissen: vordefinierte und benutzerdefinierte. Vordefinierte Ereignisse sind die Ereignisse, die diese Klasse [COleControl](../mfc/reference/colecontrol-class.md) automatisch behandelt. Eine vollständige Liste der vordefinierten Ereignissen, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen vordefinierter Ereignisse](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Benutzerdefinierte Ereignisse können ein Steuerelement die Möglichkeit, den Container zu benachrichtigen, wenn eine Aktion, die speziell für dieses Steuerelement ausgeführt wird. Beispiele umfassen eine Änderung in den internen Zustand eines Steuerelements oder Empfang einer bestimmten Fensternachricht.  
  
 Für das Steuerelement ordnungsgemäß Ereignisse ausgelöst werden muss die Steuerelementklasse jedes Ereignis des Steuerelements auf eine Memberfunktion zuordnen, die aufgerufen werden soll, wenn das zugehörige Ereignis auftritt. Dieser Zuordnungsmechanismus (Event-Zuordnung bezeichnet) und Firmennetzwerk zu Informationen über das Ereignis kann Visual Studio problemlos zugreifen und diese bearbeiten die Ereignisse des Steuerelements. Diese ereigniszuordnung wird deklariert, indem das folgende Makro, befindet sich in der Kopfzeile (. H)-Datei von der Steuerelement-Klassendeklaration:  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]  
  
 Nachdem die ereigniszuordnung deklariert wurde, muss er in der Implementierung des Steuerelements definiert werden (. CPP)-Datei. Die folgenden Codezeilen definieren die ereigniszuordnung, sodass das Steuerelement bestimmte Ereignisse ausgelöst werden:  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]  
  
 Wenn Sie MFC-ActiveX-Steuerelement-Assistenten verwenden, um das Projekt zu erstellen, fügt automatisch die folgenden Zeilen hinzu. Wenn Sie nicht die MFC-ActiveX-Steuerelement-Assistenten verwenden, müssen Sie die folgenden Zeilen manuell hinzufügen.  
  
 Mit der Klassenansicht können Sie vordefinierte Ereignisse, die von der Klasse unterstützt hinzufügen `COleControl` oder benutzerdefinierte Ereignisse, die Sie definieren. Für jedes neue Ereignis hinzugefügt Klassenansicht automatisch den ordnungsgemäßen Eintrag ereigniszuordnung für das Steuerelement und des Steuerelements. IDL-Datei.  
  
 Zwei andere Artikel werden Ereignisse im Detail beschrieben:  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
