---
title: Steuerleisten | Microsoft Docs
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
ms.openlocfilehash: bd25089594d31de21a3a315d997ee01111aff4fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347898"
---
# <a name="control-bars"></a>Steuerleisten
"Steuerleiste" ist der allgemeine Name für Symbolleisten, Statusleisten und Dialogleisten. MFC-Klassen `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar`, und **CReBar** Klasse ableiten [CControlBar](../mfc/reference/ccontrolbar-class.md), der ihre allgemeine Funktionen implementiert.  
  
 Steuerleisten sind Fenster, die Zeilen der Steuerelemente angezeigt, mit dem Benutzer können Optionen auswählen, Ausführen von Befehlen oder Programminformationen zu erhalten. Steuerleisten Anweisungstypen Dialogleisten, Symbolleisten und Statusleisten.  
  
-   Symbolleisten in der Klasse [CToolBar](../mfc/reference/ctoolbar-class.md)  
  
-   Statusleisten, in der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md)  
  
-   Dialogleisten in Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md)  
  
-   Infoleisten in der Klasse [CReBar](../mfc/reference/crebar-class.md)  
  
> [!IMPORTANT]
>  Ab MFC 4.0 werden Symbolleisten, Statusleisten und QuickInfos mit implementiert Systemfunktionen, die in der comctl32.dll anstelle der vorherigen, MFC-spezifischen Implementierung implementiert. MFC-Version 6.0 **CReBar**, die auch comctl32.dll-Funktionalität umschließt hinzugefügt wurde.  
  
 Führen Sie die kurze Einführungen in die Steuerleiste Typen. Weitere Informationen finden Sie unter den Links unten.  
  
## <a name="control-bars"></a>Steuerleisten  
 Steuerleisten erweitern erheblich Verwendbarkeit eines Programms schnell, mit nur einem Schritt Befehlsaktionen bereitstellen. Klasse `CControlBar` stellt die allgemeine Funktionen aller Symbolleisten, Statusleisten und Dialogleisten bereit. `CControlBar` Stellt die Funktionalität zum Positionieren der Steuerleiste in seiner übergeordneten Rahmenfensters bereit. Da eine Steuerleiste, die in der Regel ein untergeordnetes Fenster eines übergeordneten Rahmenfensters ist, ist es ein gleichgeordnetes "Element" auf der Clientansicht oder des MDI-Clients des Rahmenfensters. Eine Steuerleiste Objekt verwendet Informationen Clientrechteck des übergeordneten Fensters, um sich selbst zu positionieren. Klicken Sie dann ändert es des übergeordneten Elements verbleibenden Clientfenster Rechteck, damit der Clientansicht oder des MDI-Client-Fenster den Rest des Clientfensters ausgegeben wird.  
  
> [!NOTE]
>  Wenn eine Schaltfläche auf der Steuerleiste besitzt eine **Befehl** oder **UPDATE_COMMAND_UI** Handler auf, das Framework automatisch die Schaltfläche deaktiviert.  
  
## <a name="toolbars"></a>Symbolleisten  
 Eine Symbolleiste ist eine Steuerleiste, die eine Zeile mit Bitmapschaltflächen anzeigt, die Befehle auszuführen. Drücken eine Symbolleisten-Schaltfläche entspricht der Auswahl eines Menüelements; Er ruft den gleichen Handler, ein Menüelement zugeordnet werden, wenn das Menüelement die gleiche ID wie die Symbolleisten-Schaltfläche verfügt. Die Schaltflächen können angezeigt und verhält sich wie Druckknöpfe, Optionsfelder und Kontrollkästchen konfiguriert werden. Eine Symbolleiste ist in der Regel am oberen Rand eines Rahmenfensters ausgerichtet, aber eine MFC-Symbolleiste kann "andocken" auf jeder Seite des übergeordneten Fensters oder "float" in einem eigenen Minirahmenfenster. Eine Symbolleiste kann auch "float" und können Sie seine Größe ändern und mit der Maus ziehen. Eine Symbolleiste kann auch QuickInfos anzeigen, wenn der Benutzer die Maus über die Schaltflächen der Symbolleiste bewegt. Eine QuickInfo ist eine kleine Popupfenster, der den Zweck der Schaltfläche kurz beschreibt.  
  
> [!NOTE]
>  Ab MFC 4.0-Klasse [CToolBar](../mfc/reference/ctoolbar-class.md) der allgemeinen Windows-Symbolleisten-Steuerelements verwendet. Ein `CToolBar` enthält eine [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md). Ältere Symbolleisten werden weiterhin unterstützt. Finden Sie im Artikel [Symbolleisten](../mfc/mfc-toolbar-implementation.md).  
  
## <a name="status-bars"></a>Statusleisten  
 Eine Statusleiste ist eine Steuerleiste, die enthält Bereiche der Ausgabe von Text, oder "Indikatoren" genannt. Die Ausgabebereiche werden häufig als Nachricht Linien und als Statusindikatoren verwendet. Nachricht zählen Zeile die Hilfetext Befehlszeilen, die dem ausgewählten Menü oder die Befehle der Hilfesymbolleiste im linken Bereich der vom MFC-Anwendungs-Assistenten erstellte Standard-Statusleiste kurz erläutert. Beispiele für Statusanzeigen umfassen Rollen, NUM- und andere Schlüssel. Statusleisten sind in der Regel an den unteren Rand eines Rahmenfensters ausgerichtet. Siehe Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md) und Klasse [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).  
  
## <a name="dialog-bars"></a>Dialogleisten  
 Eine Dialogleiste ist eine Steuerleiste, die basierend auf einer Dialogfeldvorlagen-Ressource mit der Funktionalität eines nicht modalen Dialogfelds an. Dialogleisten darf Windows, benutzerdefinierte oder ActiveX-Steuerelemente. Wie in einem Dialogfeld kann der Benutzer zwischen den Steuerelementen auf der Registerkarte. Dialogleisten können nach oben, unten, links oder rechts Rand eines Rahmenfensters ausgerichtet werden, und sie können auch in ihre eigenen Rahmenfenster umfließt. Siehe Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md).  
  
## <a name="rebars"></a>Infoleisten  
 Ein [Grundleisten](../mfc/using-crebarctrl.md) ist eine Steuerleiste, die andocken, Layout, Status und Persistenz Informationen für Grundleisten-Steuerelemente bereitstellt. Ein Grundleisten-Objekt kann eine Vielzahl von untergeordnete Fenster, in der Regel andere Steuerelemente, einschließlich Bearbeitungsfelder, Symbolleisten und Listenfelder enthalten. Ein Grundleisten-Objekt kann über eine angegebene Bitmap zugehöriges untergeordnetes Fenster anzuzeigen. Es kann automatisch oder manuell geändert werden durch Klicken oder ziehen die Ziehpunktleiste. Siehe Klasse [CReBar](../mfc/reference/crebar-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)
