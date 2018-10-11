---
title: Hinzufügen einer Membervariablen (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.member.variable
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec9409067793da0e0a89be668f57e86588bdc2d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447315"
---
# <a name="adding-a-member-variable--visual-c"></a>Hinzufügen einer Membervariablen (Visual C++)

Mithilfe der Klassenansicht können Sie einer Klasse eine Membervariable hinzufügen. Membervariablen können generisch sein oder für [Datenaustausch und Datenvalidierung](../mfc/dialog-data-exchange-and-validation.md) verwendet werden. Der Assistent für Datenmembervariablen ist spezifisch dafür ausgelegt, die relevanten Informationen zu verwenden, um Elemente an den entsprechenden Stellen in Quelldateien einzufügen. Sie können eine Membervariable aus dem [Dialog-Editor](../windows/dialog-editor.md) oder der [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) in die [Ressourcenansicht](../windows/resource-view-window.md) hinzufügen.

> [!NOTE]
>  Wenn Sie ein Dialogfeld entwerfen und implementieren, kann es sich als effizienter erweisen, den Dialog-Editor zum Hinzufügen der Dialogfeld-Steuerelemente zu verwenden und dann die Membervariablen der Steuerelemente zu implementieren.

### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>So fügen Sie einem Dialogfeld-Steuerelement in der Ressourcenansicht eine Membervariable mithilfe des Assistenten zum Hinzufügen von Membervariablen hinzu

1. Erweitern Sie den Projektknoten und den Dialogknoten in der Ressourcenansicht, um die Liste der Dialogfelder des Projekts anzuzeigen.

1. Doppelklicken Sie auf das Dialogfeld, dem Sie die Membervariable hinzufügen möchten, um es im Dialog-Editor zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Steuerelement im Dialogfeld, das im Dialog-Editor angezeigt wird, das der Membervariable hinzugefügt werden soll.

1. Klicken Sie im Kontextmenü auf **Variable hinzufügen**, um den [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) anzuzeigen.

   > [!NOTE]
   > In der **Steuerelement-ID** wird bereits ein Standardwert angegeben.

1. Geben Sie die Informationen in den entsprechenden Feldern des Assistenten an. Weitere Informationen finden Sie unter [Dialog Box Controls and Variable Types (Steuerelemente für Dialogfelder und Variablentypen)](../ide/dialog-box-controls-and-variable-types.md).

1. Klicken Sie auf **Fertig stellen**, um dem Projekt die Definition und den Implementierungscode hinzuzufügen und den Assistenten zu schließen.

### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>So fügen Sie eine Membervariable aus der Klassenansicht mithilfe des Assistenten zum Hinzufügen von Membervariablen hinzu

1. Erweitern Sie in der [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) den Projektknoten, um die Projektklassen anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf die Klasse, der eine Variable hinzugefügt werden soll.

1. Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Variable hinzufügen**, um den Assistenten zum Hinzufügen von Membervariablen anzuzeigen.

1. Geben Sie die Informationen in den entsprechenden Feldern des Assistenten an. Ausführliche Informationen finden Sie unter [Add Member Variable Wizard (Assistent zum Hinzufügen von Membervariablen)](../ide/add-member-variable-wizard.md).

1. Klicken Sie auf **Fertig stellen**, um dem Projekt die Definition und den Implementierungscode hinzuzufügen und den Assistenten zu schließen.

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)<br>
[Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)<br>
[MFC Message Handler (MFC-Meldungshandler)](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../ide/navigating-the-class-structure-visual-cpp.md)