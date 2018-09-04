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
ms.openlocfilehash: d20611d2cc5e4b391e2dafdef614dd5173d32ef7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207297"
---
# <a name="adding-a-member-variable--visual-c"></a>Hinzufügen einer Membervariablen (Visual C++)
Mithilfe der Klassenansicht können Sie einer Klasse eine Membervariable hinzufügen. Membervariablen können generisch sein oder für [Datenaustausch und Datenvalidierung](../mfc/dialog-data-exchange-and-validation.md) verwendet werden. Der Assistent für Datenmembervariablen ist spezifisch dafür ausgelegt, die relevanten Informationen zu verwenden, um Elemente an den entsprechenden Stellen in Quelldateien einzufügen. Sie können eine Membervariable aus dem [Dialog-Editor](../windows/dialog-editor.md) oder der [Klassenansicht](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) in die [Ressourcenansicht](../windows/resource-view-window.md) hinzufügen.  
  
> [!NOTE]
>  Wenn Sie ein Dialogfeld entwerfen und implementieren, kann es sich als effizienter erweisen, den Dialog-Editor zum Hinzufügen der Dialogfeld-Steuerelemente zu verwenden und dann die Membervariablen der Steuerelemente zu implementieren.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>So fügen Sie einem Dialogfeld-Steuerelement in der Ressourcenansicht eine Membervariable mithilfe des Assistenten zum Hinzufügen von Membervariablen hinzu  
  
1.  Erweitern Sie den Projektknoten und den Dialogknoten in der Ressourcenansicht, um die Liste der Dialogfelder des Projekts anzuzeigen.  
  
2.  Doppelklicken Sie auf das Dialogfeld, dem Sie die Membervariable hinzufügen möchten, um es im Dialog-Editor zu öffnen.  
  
3.  Klicken Sie mit der rechten Maustaste auf das Steuerelement im Dialogfeld, das im Dialog-Editor angezeigt wird, das der Membervariable hinzugefügt werden soll.  
  
4.  Klicken Sie im Kontextmenü auf **Variable hinzufügen**, um den [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) anzuzeigen.  
  
    > [!NOTE]
    >  In der **Steuerelement-ID** wird bereits ein Standardwert angegeben.  
  
5.  Geben Sie die Informationen in den entsprechenden Feldern des Assistenten an. Weitere Informationen finden Sie unter [Dialog Box Controls and Variable Types (Steuerelemente für Dialogfelder und Variablentypen)](../ide/dialog-box-controls-and-variable-types.md).  
  
6.  Klicken Sie auf **Fertig stellen**, um dem Projekt die Definition und den Implementierungscode hinzuzufügen und den Assistenten zu schließen.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>So fügen Sie eine Membervariable aus der Klassenansicht mithilfe des Assistenten zum Hinzufügen von Membervariablen hinzu  
  
1.  Erweitern Sie in der [Klassenansicht](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) den Projektknoten, um die Projektklassen anzuzeigen.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Klasse, der eine Variable hinzugefügt werden soll.  
  
3.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Variable hinzufügen**, um den Assistenten zum Hinzufügen von Membervariablen anzuzeigen.  
  
4.  Geben Sie die Informationen in den entsprechenden Feldern des Assistenten an. Ausführliche Informationen finden Sie unter [Add Member Variable Wizard (Assistent zum Hinzufügen von Membervariablen)](../ide/add-member-variable-wizard.md).  
  
5.  Klicken Sie auf **Fertig stellen**, um dem Projekt die Definition und den Implementierungscode hinzuzufügen und den Assistenten zu schließen.  
  
## <a name="see-also"></a>Siehe auch  
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding a Class (Hinzufügen einer Klasse)](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC Message Handler (MFC-Meldungshandler)](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigating the Class Structure (Navigieren in der Klassenstruktur)](../ide/navigating-the-class-structure-visual-cpp.md)