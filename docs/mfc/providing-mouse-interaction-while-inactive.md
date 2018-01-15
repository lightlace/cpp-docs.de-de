---
title: Bereitstellen von Mausinteraktionen in inaktiven | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2f8991b6cc827c35c94b0989ef82e32422fd5c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="providing-mouse-interaction-while-inactive"></a>Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen
Wenn das Steuerelement nicht sofort aktiviert ist, dennoch sollten Sie verarbeitet `WM_SETCURSOR` und `WM_MOUSEMOVE` Nachrichten verwenden, auch wenn das Steuerelement kein eigenes Fenster hat. Dies geschieht durch Aktivieren der `COleControl`des Implementierung der `IPointerInactive` -Schnittstelle, die standardmäßig deaktiviert ist. (Siehe die *ActiveX SDK* eine Beschreibung dieser Schnittstelle.) Einschließen, um es zu ermöglichen, die `pointerInactive` -Flag in der Gruppe von Flags, die zurückgegebene [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 Der Code auf dieses Flag einschließen, wird automatisch generiert, wenn Sie die Option der **Mauszeiger Benachrichtigungen bei inaktiven** auf die option der [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite zum Erstellen des Steuerelements mit der **MFC-ActiveX-Steuerelement-Assistent**.  
  
 Wenn die `IPointerInactive` Schnittstelle aktiviert ist, die Container-Delegaten `WM_SETCURSOR` und `WM_MOUSEMOVE` Nachrichten darauf. `COleControl`die Implementierung der `IPointerInactive` sendet die Nachrichten über die meldungszuordnung des Steuerelements nach dem Anpassen der Maus entsprechend koordiniert. Die Nachrichten wie gewöhnliche fenstermeldungen kann verarbeitet werden, indem Sie die entsprechenden Einträge an die meldungszuordnung. Vermeiden Sie in Ihrer Handler für diese Nachrichten, die Verwendung der `m_hWnd` Membervariablen gespeichert (oder eine Memberfunktion leiten, der verwendet wird) ohne zunächst geprüft wird, die ihr Wert nicht ist **NULL**.  
  
 Sie sollten auch ein Inaktives Steuerelement das Ziel einer OLE-Drag & Drop-Operation sein soll. Dies erfordert, aktivieren das Steuerelement zum Zeitpunkt, den der Benutzer auf, ein Objekt bewegt, damit das Fenster des Steuerelements als Ablageziel registriert werden kann. Überschreiben, um dazu führen, dass die Aktivierung, um während eines Ziehvorgangs [COleControl:: GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy), und Zurückgeben der **POINTERINACTIVE_ACTIVATEONDRAG** Kennzeichen:  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 Aktivieren der `IPointerInactive` Schnittstelle in der Regel bedeutet, dass Sie das Steuerelement für die Verarbeitung von Maus Nachrichten jederzeit geeignet sein soll. Dieses Verhalten in einem Container abgerufen wird, die nicht unterstützt die `IPointerInactive` -Schnittstelle, benötigen Sie das Steuerelement, das immer aktiviert werden, wenn sichtbar ist, was bedeutet, dass das Steuerelement enthalten sollte die **OLEMISC_ACTIVATEWHENVISIBLE** zwischen kennzeichnen den sonstige Flags. Um zu verhindern, dass dieses Flag aus Effekt in einem Container durchzuführen, unterstützt jedoch `IPointerInactive`, Sie können auch angeben, die **OLEMISC_IGNOREACTIVATEWHENVISIBLE** Kennzeichen:  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

