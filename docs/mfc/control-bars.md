---
title: Steuerleisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8583b0ceba041ba9b99cb78e523d78bba71414a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439626"
---
# <a name="control-bars"></a>Steuerleisten

"" Ist der allgemeine Name für Symbolleisten, Statusleisten und Dialogleisten. MFC-Klassen `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar`, und `CReBar` Klasse abgeleitet [CControlBar](../mfc/reference/ccontrolbar-class.md), der ihre allgemeine Funktionen implementiert.

Steuerleisten sind Fenster, die Reihen von Steuerelementen angezeigt, mit dem Benutzer können Optionen auswählen, führen Sie Befehle oder erhalten Informationen zum Programm, an. Steuerleisten zählen Dialogleisten, Symbolleisten und Statusleisten.

- Symbolleisten in der Klasse [CToolBar](../mfc/reference/ctoolbar-class.md)

- Statusleisten, in der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md)

- Dialogleisten in der Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md)

- Infoleisten in der Klasse [CReBar](../mfc/reference/crebar-class.md)

> [!IMPORTANT]
>  Ab MFC-Version 4.0, Symbolleisten, Statusleisten und Tools werden Tipps implementiert, mithilfe von Systemfunktionen in implementiert die *comctl32.dll* anstelle der vorherigen, MFC-spezifischen Implementierung. MFC-Version 6.0 `CReBar`, die auch comctl32.dll Funktionalität umschließt wurde hinzugefügt.

Führen Sie die kurze Einführungen in die Typen der Steuerleiste. Weitere Informationen finden Sie unter folgenden Links.

## <a name="control-bars"></a>Steuerleisten

Steuerleisten zur Verbesserung der erheblich eines Programms Verwendbarkeit schnell, Befehlsaktionen in einem Schritt bereitstellen. Klasse `CControlBar` stellt die allgemeine Funktionalität alle Symbolleisten, Statusleisten und Dialogleisten bereit. `CControlBar` Stellt die Funktionalität für die Positionierung der Steuerleiste des übergeordneten Frame-Fensters bereit. Da eine Steuerleiste, die in der Regel ein untergeordnetes Fenster eines übergeordneten Rahmenfensters ist, ist es ein gleichgeordnetes "Element" auf der Clientansicht oder des MDI-Clients des Rahmenfensters. Ein Objekt der Steuerleiste verwendet Informationen über Clientrechteck des übergeordneten Fensters zum eigenen positionieren. Und dann die verbleibenden-Clientfenster-Rechteck des übergeordneten Elements ändert, damit der Clientansicht oder des MDI-Clientfenster den Rest der Clientfenster füllt.

> [!NOTE]
>  Wenn eine Schaltfläche auf der Steuerleiste besitzt eine **Befehl** oder **wähle ich UPDATE_COMMAND_UI** Handler auf, das Framework automatisch die Schaltfläche deaktiviert.

## <a name="toolbars"></a>Symbolleisten

Eine Symbolleiste ist eine Steuerleiste, die eine Zeile mit Bitmapschaltflächen anzeigt, die Befehle ausführen. Eine Symbolleisten-Schaltfläche drücken entspricht der Auswahl eines Menüelements. Sie ruft den gleichen Handler an ein Menüelement zugeordnet ist, wenn das Menüelement die gleiche ID wie die Symbolleisten-Schaltfläche verfügt. Die Schaltflächen können angezeigt und verhält sich wie Druckknöpfe, Kontrollkästchen oder Optionsfelder konfiguriert werden. Eine Symbolleiste ist in der Regel am oberen Rand eines Rahmenfensters ausgerichtet, aber eine MFC-Symbolleiste kann "andocken" auf jeder Seite des übergeordneten Fensters oder "float" in einem eigenen kleinen Rahmenfenster-Fenster. Eine Symbolleiste kann auch "float", und Sie seine Größe ändern können, und ziehen Sie es mit der Maus. Eine Symbolleiste kann auch QuickInfos angezeigt, wenn der Benutzer die Maus über die Schaltflächen der Symbolleiste bewegt. Eine QuickInfo ist eine kleine Popupfenster, das beschreibt den Zweck der Schaltfläche.

> [!NOTE]
>  Ab MFC 4.0, Klasse [CToolBar](../mfc/reference/ctoolbar-class.md) verwendet die allgemeine Windows-Symbolleisten-Steuerelement. Ein `CToolBar` enthält eine [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md). Ältere Symbolleisten werden jedoch weiterhin unterstützt. Finden Sie im Artikel [Symbolleisten](../mfc/mfc-toolbar-implementation.md).

## <a name="status-bars"></a>Statusleisten

Eine Statusleiste ist eine Steuerleiste, die Text-Ausgabebereiche oder "Indikatoren" enthält Die Ausgabebereiche werden häufig als Nachricht Zeilen und Statusindikatoren verwendet. Beispiele für Zeile enthalten die hilfemeldung Befehlszeilen, die dem ausgewählten Menü oder die Befehle der Hilfesymbolleiste im Bereich der vom MFC-Anwendungs-Assistenten erstellten Standard-Statusleiste am weitesten links stehende kurz erläutern. Beispiele für Statusanzeigen enthalten, die Rollen-Taste, NUM- und andere Schlüssel. StatusBar-Steuerelemente werden in der Regel am unteren Rand eines Rahmenfensters ausgerichtet. Finden Sie unter Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md) und Klasse [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).

## <a name="dialog-bars"></a>Dialogleisten

Eine Dialogleiste ist eine Steuerleiste, die basierend auf einer Dialogfeldvorlagen-Ressource, mit der Funktionalität eines nicht modalen Dialogfelds an. Dialogleisten darf Windows, benutzerdefinierte oder ActiveX-Steuerelemente. Wie in einem Dialogfeld kann der Benutzer zwischen den Steuerelementen Registerkarte. Dialogleisten, oben, unten, links oder rechts Rand eines Rahmenfensters ausgerichtet werden können, und sie können auch in ihre eigenen Rahmenfenster abgedockt werden. Finden Sie unter Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md).

## <a name="rebars"></a>Infoleisten

Ein [Infoleiste](../mfc/using-crebarctrl.md) ist eine Steuerleiste, die andocken, Layout, Status und Persistenz Informationen für Grundleisten-Steuerelemente bereitstellt. Einem Grundleisten-Objekt kann es sich um eine Vielzahl untergeordneter Fenster, in der Regel andere Steuerelemente, einschließlich Bearbeitungsfelder, Symbolleisten und Listenfelder enthalten. Zugehöriges untergeordnetes Fenster kann von einem Grundleisten-Objekt über eine angegebene Bitmap anzeigen. Dann kann automatisch oder manuell geändert werden durch Klicken oder ziehen die Ziehpunktleiste. Finden Sie unter Klasse [CReBar](../mfc/reference/crebar-class.md).

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
