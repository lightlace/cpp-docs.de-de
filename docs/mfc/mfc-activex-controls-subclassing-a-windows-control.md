---
title: 'MFC-ActiveX-Steuerelemente: Erstellen von Unterklassen für ein Windows-Steuerelement | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- precreatewindow
- IsSubclassed
dev_langs:
- C++
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd03babd97033495ecfa84817938103cde05a73
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081705"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC-ActiveX-Steuerelemente: Erstellen einer Fenstersteuerelement-Unterklasse

Dieser Artikel beschreibt den Prozess zum Erstellen von Unterklassen für eine allgemeine Windows-Steuerelement, um ein ActiveX-Steuerelement zu erstellen. Unterklassen aus einer vorhandenen Windows-Steuerelement ist eine schnelle Möglichkeit, ein ActiveX-Steuerelement entwickeln. Das neue Steuerelement müssen die Funktionen von der untergeordnetes Windows-Steuerelement, z. B. das Zeichnen von und reagieren auf Mausklicks. Die MFC-ActiveX-Steuerelemente Beispiel [Schaltfläche](../visual-cpp-samples.md) ist ein Beispiel für das Erstellen von Unterklassen für ein Windows-Steuerelement.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen über moderne Technologien, die ActiveX Ersetzen eines finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Um eine Unterklasse einer Windows-Steuerelement können führen Sie die folgenden Aufgaben aus:

- [Überschreiben Sie die IsSubclassedControl und PreCreateWindow-Memberfunktionen der COleControl](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [Ändern Sie die OnDraw-Member-Funktion](#_core_modifying_the_ondraw_member_function)

- [Behandeln Sie alle ActiveX-Steuerelement-Nachrichten (OCM) reflektiert, um das Steuerelement](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > Ein Großteil dieser Arbeit erfolgt vom ActiveX-Steuerelement-Assistenten bei Auswahl des Steuerelements in Unterklassen unterteilt werden mithilfe der **übergeordneten Fenster-Klasse auswählen** Dropdown-Liste auf die **Steuerelementeinstellungen** Seite.

##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> Überschreiben von IsSubclassedControl und PreCreateWindow

Zum Überschreiben `PreCreateWindow` und `IsSubclassedControl`, fügen Sie die folgenden Codezeilen die **geschützt** Teil der Klassendeklaration des Steuerelements:

[!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

In der Implementierungsdatei des Steuerelements (. CPP), fügen Sie die folgenden Codezeilen die zwei außer Kraft gesetzte Funktionen implementiert:

[!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

Beachten Sie, dass in diesem Beispiel die Windows Steuerelement Schaltfläche wird angegeben, `PreCreateWindow`. Allerdings können alle standardmäßigen Windows-Steuerelemente als Unterklasse definiert werden. Weitere Informationen zu Windows-Standardsteuerelemente, finden Sie unter [Steuerelemente](../mfc/controls-mfc.md).

Beim Erstellen von Unterklassen für ein Windows-Steuerelement, empfiehlt es sich um bestimmte Fensterstil (WS_) oder erweiterten Stil (WS_EX_)-Flags, die verwendet werden, erstellen Sie das Fenster des Steuerelements anzugeben. Sie können Werte für diese Parameter Festlegen der `PreCreateWindow` Member-Funktion, durch Ändern der `cs.style` und die `cs.dwExStyle` Struktur Felder. Änderungen an diesen Feldern sollten vorgenommen werden, mithilfe einer **oder** -Vorgang, um die Standardkennzeichen zu erhalten, die von der Klasse festgelegt werden `COleControl`. Z. B. wenn das Steuerelement das Schaltflächen-Steuerelement Unterklassen wird und das Steuerelement als ein Kontrollkästchen angezeigt werden soll, legen Sie die folgende Codezeile in der Implementierung des `CSampleCtrl::PreCreateWindow`, bevor Sie die return-Anweisung:

[!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

Dieser Vorgang fügt das Flag für den BS_CHECKBOX-Stil, bleiben die Standard-Style-Flag (WS_CHILD) der Klasse `COleControl` intakt.

##  <a name="_core_modifying_the_ondraw_member_function"></a> Ändern die OnDraw-Member-Funktion

Wunsch Ihrer Unterklasse-Steuerelement die gleiche Darstellung als das entsprechende Windows-Steuerelement, zu der `OnDraw` Member-Funktion für das Steuerelement sollte enthalten lediglich einen Aufruf der `DoSuperclassPaint` Member-Funktion, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

Die `DoSuperclassPaint` Memberfunktion wird durch implementiert `COleControl`, verwendet die Fensterprozedur des Windows-Steuerelements das Steuerelement im angegebenen Gerätekontext, innerhalb des umschließenden Rechtecks gezeichnet. Dadurch werden das Steuerelement sichtbar, selbst wenn diese nicht aktiviert ist.

> [!NOTE]
>  Die `DoSuperclassPaint` Member-Funktion funktioniert nur mit Steuerelementtypen, die einen Gerätekontext, die als übergeben werden, ermöglichen die *wParam-Parameter* von eine WM_PAINT-Meldung. Dies schließt einige der Windows-Standardsteuerelemente, z. B. die SCROLLLEISTE und die Schaltfläche, und die Standardsteuerelemente. Sie müssen für Steuerelemente, die dieses Verhalten nicht unterstützen, geben Sie Ihren eigenen Code ein Inaktives Steuerelement ordnungsgemäß angezeigt.

##  <a name="_core_handling_reflected_window_messages"></a> Behandeln von reflektierten Fenstermeldungen

Windows-Steuerelemente senden bestimmter Windows-Meldungen in der Regel für ihre übergeordnete Fenster. Einige dieser Nachrichten, z. B. WM_COMMAND, bieten die Benachrichtigung über eine Aktion durch den Benutzer. Andere, z. B. WM_CTLCOLOR, dienen zum Abrufen von Informationen über das übergeordnete Fenster. Ein ActiveX-Steuerelement kommuniziert mithilfe anderer Methoden in der Regel mit dem übergeordneten Fenster. Benachrichtigungen werden durch Auslösen von Ereignissen (ereignisbenachrichtigungen senden) kommuniziert, und erhalten Sie Informationen zu den Steuerelementcontainer durch Zugreifen auf Umgebungseigenschaften des Containers. Da diese Kommunikationstechniken vorhanden sind, sollten nicht ActiveX-Steuerelementcontainer vom Steuerelement gesendete fenstermeldungen zu verarbeiten.

Um zu verhindern, dass den Container erhalten die Windows-Nachrichten, die von einem untergeordnetes Windows-Steuerelement gesendet `COleControl` erstellt ein zusätzliches Fenster, die als übergeordnete Element des Steuerelements verwendet werden. Diese zusätzliche Fenster, mit der Bezeichnung "Reflector", wird nur für ein ActiveX-Steuerelement erstellt, dass eine Windows-Unterklassen steuern und verfügt über die gleiche Größe und Position wie das Steuerelement. Das Fenster "Reflector" fängt die bestimmte Windows-Meldungen ab und sendet sie an das Steuerelement. Steuerelements in der Fensterprozedur auf, kann dann diese reflektierten Meldungen verarbeiten, indem Aktionen, die für ein ActiveX-Steuerelement (z. B. das Auslösen eines Ereignisses). Finden Sie unter [wiedergegeben Fenstermeldungs-IDs](../mfc/reflected-window-message-ids.md) eine Liste der abgefangenen Windows Nachrichten und die entsprechenden reflektierten Meldungen.

Ein ActiveX-Steuerelementcontainer kann entworfen werden, zum Durchführen der Nachricht Reflektion selbst, wodurch die Notwendigkeit entfällt `COleControl` um das Fenster "Reflector" und reduzieren die Laufzeit-overhead für ein untergeordnetes Windows-Steuerelement zu erstellen. `COleControl` erkennt, ob der Container dieser Funktion erfüllt, indem Sie für eine MessageReflect ambient-Eigenschaft mit einem Wert von **"true"**.

Um eine reflektierte Meldung zu behandeln, die Steuerelement-meldungszuordnung wird ein Eintrag hinzugefügt, und implementieren Sie eine Handlerfunktion. Da reflektierte Meldungen, die nicht Teil der Standardsatz von Nachrichten, die von Windows definiert sind, solche Meldungshandler hinzufügen die Klassenansicht wird nicht unterstützt. Allerdings ist es nicht schwierig, einen Handler manuell hinzufügen.

Zum Hinzufügen ein meldungshandlers für eine reflektierte Meldung manuell wie folgt:

- In der Steuerelementklasse. H-Datei, eine Handlerfunktion deklarieren. Die Funktion müssen Rückgabetyp **LRESULT** und zwei Parameter, mit Typen **WPARAM** und **LPARAM**bzw. Zum Beispiel:

   [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- In der Steuerelementklasse. CPP-Datei, fügen Sie einen ON_MESSAGE-Eintrag, um die meldungszuordnung. Die Parameter dieses Eintrags sollte es sich um die Nachrichten-ID und der Name der Handlerfunktion sein. Zum Beispiel:

   [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- Auch in der. CPP-Datei, implementieren die `OnOcmCommand` Member-Funktion zum Verarbeiten der Nachricht wiedergegeben. Die *wParam* und *lParam* Parameter sind identisch mit denen der ursprünglichen Fensternachricht im.

Ein Beispiel dafür, wie wiedergegeben Nachrichten verarbeitet werden, finden Sie in dem Beispiel für die MFC-ActiveX-Steuerelemente [Schaltfläche](../visual-cpp-samples.md). Es zeigt eine `OnOcmCommand` Handler, den Benachrichtigungscode BN_CLICKED erkennt und antwortet, indem Sie das Auslösen von (senden) einer `Click` Ereignis.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

