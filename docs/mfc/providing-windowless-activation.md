---
title: Bereitstellung von Fensterloser Aktivierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e8fc079921b3f2eddd117f93ee9d2f6cad60925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441225"
---
# <a name="providing-windowless-activation"></a>Bereitstellung von fensterloser Aktivierung

Code für die Datenbankerstellung Fenster (d. h. alle beim Aufrufen Vorgänge `CreateWindow`) ist zu kostspielig, führen Sie. Ein Steuerelement, das verwaltet ein Fenster auf dem Bildschirm hat, um Nachrichten für das Fenster zu verwalten. Fensterlose Steuerelemente sind daher schneller als Steuerelemente in Windows.

Ein weiterer Vorteil der fensterlose Steuerelemente ist, dass im Gegensatz zu im Fenstermodus-Steuerelemente, fensterlose Steuerelemente transparent zeichnen und nicht rechteckige Bildschirmbereiche unterstützt. Transparentes Steuerelement ein gängiges Beispiel ist ein Text-Steuerelement mit einem transparenten Hintergrund. Die Steuerelemente zeichnet den Text, jedoch nicht auf den Hintergrund, damit die zeigt, was auch immer unterhalb des Texts wird durch. Neuere Formulare erstellen, verwenden Sie nicht rechteckige Steuerelemente, z. B. Pfeilen und runde Schaltflächen häufig.

Häufig ein Steuerelement ist nicht erforderlich, ein eigenes Fenster und kann stattdessen Windows-Dienste des Containers, vorausgesetzt, dass der Container geschrieben hat, fensterlose Objekte zu unterstützen. Fensterlose Steuerelemente sind abwärtskompatibel mit älteren Container. In älteren Container nicht geschrieben, fensterlose Steuerelemente zu unterstützen Erstellen der fensterlose Steuerelemente ein Fenster, wenn aktiv.

Da Fensterlose Steuerelemente nicht ihre eigenen Windows haben, ist der Container (der ein Fenster) für die Bereitstellung von Diensten, die andernfalls durch das Fenster des Steuerelements bereitgestellt würden verantwortlich. Wenn das Steuerelement den Tastaturfokus Abfragen, Erfassen der Maus oder einen Gerätekontext zu erhalten, werden diese Vorgänge z.B. vom Container verwaltet. Der Container leitet Benutzer eingehende Nachrichten gesendet, um das Fenster an das entsprechende fensterloses Steuerelement, mit der `IOleInPlaceObjectWindowless` Schnittstelle. (Finden Sie unter den *ActiveX SDK* eine Beschreibung dieser Schnittstelle.) `COleControl` Memberfunktionen Aufrufen dieser Dienste aus dem Container.

Um Ihr Steuerelement fensterlosen Aktivierung verwenden zu können, enthalten die **verwendet** -Flag in einem Satz von Flags, die vom [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]

Der Code auf dieses Flag einschließen, wird automatisch generiert, wenn Sie die Option der **Fensterloser Aktivierung** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC-ActiveX-Steuerelement-Assistenten auf der Seite.

Wenn fensterloser Aktivierung aktiviert ist, wird der Container eingabemeldungen des Steuerelements Delegieren `IOleInPlaceObjectWindowless` Schnittstelle. `COleControl`die Implementierung dieser Schnittstelle sendet die Nachrichten über die meldungszuordnung Ihres Steuerelements, nach dem entsprechend-die Maus anpassen Koordinaten. Sie können die Nachrichten wie gewöhnliche Meldungen Hinzufügen der entsprechenden Einträge in die nachrichtenzuordnung verarbeiten. Verwenden Sie in Ihre Handler für diese Nachrichten, die *M_hWnd* Membervariable (oder eine Memberfunktion leiten, der verwendet wird) ohne vorherige Überprüfung, die der Wert nicht **NULL**.

`COleControl` enthält die Member-Funktionen, die Mausauswahl, Tastaturfokus, Bildlauf und andere Fensterdienste aus dem Container nach Bedarf, einschließlich aufrufen:

- [GetFocus](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)

- [GetCapture](../mfc/reference/colecontrol-class.md#getcapture), [SetCapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)

- [GetDC](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)

- [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)

- [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)

- [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)

Fensterlose Steuerelemente sollten Sie immer verwenden die `COleControl` Memberfunktionen anstelle der entsprechenden `CWnd` Memberfunktionen oder deren entsprechenden Win32-API-Funktionen.

Sie sollten ein fensterloses Steuerelement das Ziel eines OLE-Drag & Drop-Vorgangs sein soll. Normalerweise erfordert dies, dass das Fenster des Steuerelements als Dropziel registriert werden. Da es sich bei dem Steuerelement kein eigenes Fenster ist, verwendet den Container ein eigenen Fenster als Drop-Ziel. Das Steuerelement stellt eine Implementierung der `IDropTarget` Schnittstelle, zu denen der Container Aufrufe zum richtigen Zeitpunkt delegieren kann. Um diese Schnittstelle für den Container verfügbar zu machen, außer Kraft setzen [COleControl:: GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget). Zum Beispiel:

[!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

