---
title: Bereitstellung von Fensterloser Aktivierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eb33f1dd9f8be8cb06cdfcc2aeecb653c2762410
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="providing-windowless-activation"></a>Bereitstellung von fensterloser Aktivierung
Fenster Erstellung Code (d. h. alle beim Aufruf von **CreateWindow**) beeinträchtigen ausführen. Ein Steuerelement, das verwaltet ein Fenster auf dem Bildschirm hat, um Nachrichten für das Fenster zu verwalten. Fensterlose Steuerelemente sind deshalb schneller als Steuerelemente in Windows.  
  
 Ein weiterer Vorteil der fensterlose Steuerelemente ist, dass im Gegensatz zu Fensterfunktionen Steuerelemente Fensterlose Steuerelemente transparent zeichnen und nicht rechteckige Bildschirmbereiche unterstützt. Ein allgemeines Beispiel für ein Steuerelement transparent ist ein Text-Steuerelement mit einem transparenten Hintergrund. Die Steuerelemente zeichnet den Text, jedoch nicht auf den Hintergrund, damit zeigt, was unter dem Text ist durch. Neuere Forms stellen häufig nicht rechteckige Steuerelemente, z. B. Pfeilen verwenden und runde Schaltflächen.  
  
 Häufig, ein Steuerelement ist es nicht erforderlich, ein eigenes Fenster und kann verwenden Sie stattdessen die Windows-Dienste des Containers, vorausgesetzt, dass der Container fensterlose Objekte unterstützen geschrieben wurde. Fensterlose Steuerelemente sind abwärtskompatibel mit älteren Containern. In älteren Containern Fensterlose Steuerelemente unterstützen nicht geschrieben werden erstellen Fensterlose Steuerelemente ein Fensters aktiven Zustand.  
  
 Da Fensterlose Steuerelemente nicht ihre eigenen Windows verfügen, ist der Container (die ein Fenster verfügt) für die Bereitstellung von Diensten, die andernfalls vom Fenster des Steuerelements bereitgestellt würden zuständig. Wenn das Steuerelement den Tastaturfokus abzufragen, Erfassen der Maus oder erhalten einen Gerätekontext, werden diese Vorgänge vom Container verwaltet. Der Container leitet Benutzer eingehende Nachrichten gesendet, um das Fenster auf das entsprechende fensterloses Steuerelement mithilfe der `IOleInPlaceObjectWindowless` Schnittstelle. (Siehe die *ActiveX SDK* eine Beschreibung dieser Schnittstelle.) `COleControl` Memberfunktionen Aufrufen dieser Dienste aus dem Container.  
  
 Um das Steuerelement fensterlosen Aktivierung verwenden zu können, enthalten die **verwendet** -Flag in der Gruppe von Flags, die zurückgegebene [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]  
  
 Der Code auf dieses Flag einschließen, wird automatisch generiert, wenn Sie die Option der **fensterlose Aktivierung** auf die option der [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite des MFC-ActiveX-Steuerelement-Assistenten.  
  
 Wenn fensterloser Aktivierung aktiviert ist, wird der Container eingehende Nachrichten an des Steuerelements Delegieren `IOleInPlaceObjectWindowless` Schnittstelle. `COleControl`die Implementierung dieser Schnittstelle übermittelt die Nachrichten über das Steuerelement meldungszuordnung, nach dem Anpassen der Maus entsprechend koordiniert. Sie können die Nachrichten wie gewöhnliche fenstermeldungen, verarbeiten, durch Hinzufügen der entsprechenden Einträge in die meldungszuordnung. Vermeiden Sie in Ihrer Handler für diese Nachrichten, die Verwendung der `m_hWnd` Membervariablen gespeichert (oder eine Memberfunktion leiten, der verwendet wird) ohne zunächst geprüft wird, die ihr Wert nicht ist **NULL**.  
  
 `COleControl`bietet Memberfunktionen, die Mausauswahl, den Tastaturfokus, Durchführen eines Bildlaufs und andere Fensterdienste aus dem Container nach Bedarf, einschließlich aufrufen:  
  
-   [GetFocus](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)  
  
-   [GetCapture](../mfc/reference/colecontrol-class.md#getcapture), [SetCapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)  
  
-   [GetDC](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)  
  
-   [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)  
  
-   [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)  
  
-   [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)  
  
 Sie sollten immer verwenden, in Fensterlose Steuerelemente der `COleControl` Memberfunktionen anstelle der entsprechenden `CWnd` Memberfunktionen oder ihre zugehörigen Win32-API-Funktionen.  
  
 Sie sollten ein fensterloses Steuerelement das Ziel einer OLE-Drag & Drop-Operation sein soll. Normalerweise würde dies erfordert, dass das Fenster des Steuerelements als Ablageziel registriert werden. Da das Steuerelement kein eigenes Fenster hat, verwendet der Container ein eigenen Fenster als Drop-Ziel. Das Steuerelement stellt eine Implementierung von der `IDropTarget` Schnittstelle zu der der Container Aufrufe zum entsprechenden Zeitpunkt delegieren. Um diese Schnittstelle für den Container verfügbar zu machen, überschreiben [COleControl:: GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget). Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

