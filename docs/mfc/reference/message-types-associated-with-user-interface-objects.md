---
title: Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.uiobject.msgs
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
ms.openlocfilehash: 1676edf487d536d75ccd7901c5bdfa827cc143fe
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326321"
---
# <a name="message-types-associated-with-user-interface-objects"></a>Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen

Die folgende Tabelle zeigt die Typen von Objekten, die mit denen Sie arbeiten, und die Typen von Nachrichten, die zugeordnet werden.

### <a name="user-interface-objects-and-associated-messages"></a>Benutzeroberflächenobjekte und die zugehörigen Meldungen

|Objekt-ID|Meldungen|
|---------------|--------------|
|Klassennamen, die Darstellung des enthaltenden Fensters|Windows-Nachrichten geeignet, um eine [CWnd](../../mfc/reference/cwnd-class.md)-Klasse: ein Dialogfeld, Fenster, untergeordnetes Fenster, untergeordneten MDI-Fensters oder Rahmenfenster der obersten Ebene.|
|Menü oder die Tastenkombination-Bezeichner|-COMMAND-Nachricht (die Programmfunktion ausgeführt).<br />-Wähle ich UPDATE_COMMAND_UI Nachricht (aktualisiert das Menüelement dynamisch).|
|Steuerelement-ID|Benachrichtigungsmeldungen des Registersteuerelements für den Typ des ausgewählten Steuerelements.|

## <a name="see-also"></a>Siehe auch

[Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigating-the-class-structure-visual-cpp.md)
