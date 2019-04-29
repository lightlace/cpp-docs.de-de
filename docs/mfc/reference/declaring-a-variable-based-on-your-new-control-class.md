---
title: Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: b3b1a168619c1c111db3e71e1a9562d441cc710d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323007"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen

Nachdem Sie eine MFC-Steuerelement-Klasse erstellt haben, können Sie eine darauf basierende Variable deklarieren. Um einen Kontext für die neue Variable zu gewährleisten, müssen Sie den Dialog-Editor zu öffnen und bearbeiten das Dialogfeld, in dem Sie Ihr wiederverwendbare Steuerelement zu verwenden möchten. Darüber hinaus muss das Dialogfeld bereits eine Klasse zugeordnet sein. Weitere Informationen zur Verwendung des Dialog-Editors, finden Sie unter [Dialog-Editor](../../windows/dialog-editor.md).

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Zum Deklarieren einer Variablen, die basierend auf Ihrer wiederverwendbare Klasse

1. Während der Bearbeitung des Dialogfelds, ziehen Sie ein Steuerelement der gleiche Typ wie die Basisklasse des neuen Steuerelements über die Steuerelemente-Symbolleiste auf das Dialogfeld.

1. Platzieren Sie den Mauszeiger über dem Steuerelement verworfen.

1. Doppelklicken Sie bei gedrückter STRG-Taste, auf das Steuerelement.

   Die [Hinzufügen von Membervariablen](../../ide/add-member-variable-wizard.md) Dialogfeld wird angezeigt.

1. In der **Zugriff** wählen den richtigen Zugriff für das Steuerelement.

1. Klicken Sie auf die **Steuerungsvariable** Kontrollkästchen.

1. In der **Variablenname** geben einen Namen.

1. Klicken Sie unter **Kategorie**, klicken Sie auf **Steuerelement**.

1. In der **Steuerelement-ID** Liste, wählen Sie das Steuerelement, das Sie hinzugefügt haben. Die **Variablentyp** Liste sollte die richtigen Variablentyp, anzeigen und die **Steuerelementtyp** den korrekten Steuerelementtyp angezeigt.

9. In der **Kommentar** hinzu, und eine zusätzliche Anmerkung, die in Ihrem Code angezeigt werden sollen.

10. Klicken Sie auf **OK**.

## <a name="see-also"></a>Siehe auch

[Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigating-the-class-structure-visual-cpp.md)
