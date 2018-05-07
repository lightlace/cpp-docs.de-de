---
title: Deklarieren einer Variablen auf Grundlage der neuen Steuerelementklasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 677006d441c940f478b3d23744d1057667307e1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen
Nachdem Sie eine MFC-Steuerelementklasse erstellt haben, können Sie eine Variable, die darauf basieren deklarieren. Um einen Kontext für die neue Variable zu gewährleisten, müssen Sie den Dialog-Editor zu öffnen und bearbeiten das Dialogfeld, in dem Sie Ihre wiederverwendbare Steuerelement verwenden möchten. Darüber hinaus muss das Dialogfeld bereits eine Klasse zugeordnet sein. Informationen zum Verwenden des Dialog-Editors finden Sie unter [Dialog-Editor](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Zum Deklarieren einer Variablen, die basierend auf Ihrer wiederverwendbare-Klasse  
  
1.  Ziehen Sie beim Bearbeiten des Dialogfelds "" ein Steuerelement von den gleichen Typ wie die Basisklasse des neuen Steuerelements aus der Symbolleiste für Steuerelemente auf das Dialogfeld ein.  
  
2.  Platzieren Sie den Mauszeiger über dem Steuerelement gezogen.  
  
3.  Doppelklicken Sie beim Drücken der STRG-Taste auf das Steuerelement.  
  
     Die [Hinzufügen von Membervariablen](../../ide/add-member-variable-wizard.md) Dialogfeld wird angezeigt.  
  
4.  In der **Zugriff** wählen den richtigen Zugriff für das Steuerelement.  
  
5.  Klicken Sie auf die **Steuerelementvariable** Kontrollkästchen.  
  
6.  In der **Variablenname** geben einen Namen.  
  
7.  Klicken Sie unter **Kategorie**, klicken Sie auf **Steuerelement**.  
  
8.  In der **Kontroll-ID** Liste, wählen Sie das Steuerelement, das Sie hinzugefügt haben. Die **Variablentyp** Liste sollte den richtigen Variablentyp anzuzeigen und die **Steuerelementtyp** Feld sollte den richtigen Steuerelementtyp anzeigen.  
  
9. In der **Kommentar** fügen Kommentars, den Sie in Ihrem Code angezeigt werden soll.  
  
10. Klicken Sie auf **OK**.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)
