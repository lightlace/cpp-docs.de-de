---
title: Bereitstellen von Mausinteraktionen in inaktiven | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9394a3c161b82fa95de0e2ae0c590aec87493a85
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418735"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen

Wenn das Steuerelement nicht sofort aktiviert ist, immer noch sollten damit Prozess WM_SETCURSOR und WM_MOUSEMOVE-Nachrichten, Sie auch, wenn das Steuerelement kein eigenes Fenster hat. Dies kann erreicht werden, durch Aktivieren der `COleControl`die Implementierung der `IPointerInactive` -Schnittstelle, die standardmäßig deaktiviert ist. (Finden Sie unter den *ActiveX SDK* eine Beschreibung dieser Schnittstelle.) Um es zu aktivieren, fügen Sie den in den Satz von Flags, die vom [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

Der Code auf dieses Flag einschließen, wird automatisch generiert, wenn Sie die Option der **Mauszeiger Benachrichtigungen wenn inaktiv** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite herunter. erstellen das Steuerelement mit dem **MFC-ActiveX-Steuerelement-Assistent**.

Wenn die `IPointerInactive` Schnittstelle aktiviert ist, wird der Container delegiert WM_SETCURSOR und WM_MOUSEMOVE-Nachrichten an diese. `COleControl`die Implementierung von `IPointerInactive` sendet die Nachrichten über die meldungszuordnung Ihres Steuerelements, nach dem entsprechend-die Maus anpassen Koordinaten. Durch Hinzufügen der entsprechenden Einträge in die nachrichtenzuordnung kann die Nachrichten wie normale Windows-Meldungen verarbeitet werden. Verwenden Sie in Ihre Handler für diese Nachrichten, die *M_hWnd* Membervariable (oder eine Memberfunktion leiten, der verwendet wird) ohne vorherige Überprüfung, die der Wert nicht **NULL**.

Sie sollten auch ein Inaktives Steuerelement das Ziel eines OLE-Drag & Drop-Vorgangs sein soll. Dies erfordert, aktivieren das Steuerelement zum Zeitpunkt der Benutzer ein Objekt auf, bewegt, damit das Fenster des Steuerelements als Dropziel registriert werden kann. Überschreiben, um dazu führen, dass die Aktivierung während eines Ziehvorgangs [COleControl:: GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy), und geben Sie das Flag POINTERINACTIVE_ACTIVATEONDRAG zurück:

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

Aktivieren der `IPointerInactive` Schnittstelle in der Regel bedeutet, dass das Steuerelement kann mausmeldungen jederzeit verarbeiten soll. Um dieses Verhalten in einem Container zu erhalten, die nicht unterstützt die `IPointerInactive` -Schnittstelle, benötigen Sie das Steuerelement immer aktiviert, wenn sichtbar ist, was bedeutet, dass das Steuerelement sollte das Flag OLEMISC_ACTIVATEWHENVISIBLE zwischen verschiedenen Flags enthalten. Um zu verhindern, dass dieses Flag aus wirksam in einem Container, die unterstützt jedoch `IPointerInactive`, Sie können auch das Flag OLEMISC_IGNOREACTIVATEWHENVISIBLE angeben:

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

