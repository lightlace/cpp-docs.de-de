---
title: Deklarieren einer Variablen basierend auf der neuen Steuerelementklasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables, control classes
- control classes, variables
- classes [C++], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: a5777019ca87616fbb7c6a0d27140b3fabbf7fde
ms.lasthandoff: 02/24/2017

---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen
Nachdem Sie eine MFC-Steuerelementklasse erstellt haben, können Sie eine Variable, die darauf basieren deklarieren. Um einen Kontext für die neue Variable zu gewährleisten, müssen Sie Dialog-Editor zu öffnen und bearbeiten das Dialogfeld, in dem das Steuerelement wiederverwendet werden soll. Darüber hinaus muss das Dialogfeld bereits eine Klasse zugeordnet sein. Informationen zum Verwenden des Dialog-Editors finden Sie unter [Dialog-Editor](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Zum Deklarieren einer Variablen auf Grundlage Ihrer wieder verwendbare Klasse  
  
1.  Bearbeiten Sie das Dialogfeld, ziehen Sie ein Steuerelement desselben Typs als Basisklasse des neuen Steuerelements aus der Steuerelement-Symbolleiste in das Dialogfeld.  
  
2.  Platzieren Sie den Mauszeiger über dem abgelegten Steuerelement.  
  
3.  Doppelklicken Sie beim Drücken der STRG-Taste auf das Steuerelement.  
  
     Die [Hinzufügen von Membervariablen](../../ide/add-member-variable-wizard.md) das Dialogfeld wird angezeigt.  
  
4.  In der **Zugriff** wählen Sie den richtigen Zugriff für das Steuerelement.  
  
5.  Klicken Sie auf die **Steuerelementvariable** das Kontrollkästchen.  
  
6.  In der **Variablenname** Geben Sie einen Namen ein.  
  
7.  Klicken Sie unter **Kategorie**, klicken Sie auf **Steuerelement**.  
  
8.  In der **Steuerelement-ID** Liste, wählen Sie das Steuerelement, das Sie hinzugefügt haben. Die **Variablentyp** Liste sollte den richtigen Variablentyp anzuzeigen und die **Steuerelementtyp** den korrekten Steuerelementtyp angezeigt.  
  
9. In der **Kommentar** fügen einen Kommentar im Code angezeigt werden soll.  
  
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

