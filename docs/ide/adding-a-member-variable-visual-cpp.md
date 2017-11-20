---
title: "Hinzufügen einer Membervariablen (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.classes.member.variable
dev_langs: C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2722d45da00349c797d6091506fda82a06614d1c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="adding-a-member-variable--visual-c"></a>Hinzufügen einer Membervariablen (Visual C++)
Sie können eine Membervariable zu einer Klasse mit der Klassenansicht hinzufügen. Membervariablen kann entweder für [Datenaustausch und datenvalidierung](../mfc/dialog-data-exchange-and-validation.md), oder sie können generisch sein. Der Assistent Variablen Member ist speziell für nehmen die relevante Informationen und zum Einfügen von Elementen in den Quelldateien an den entsprechenden Stellen verwenden. Sie können eine Membervariable vom Hinzufügen der [Dialog-Editor](../windows/dialog-editor.md) in [Ressourcenansicht](../windows/resource-view-window.md), oder von [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
> [!NOTE]
>  Beim Entwerfen und implementieren ein Dialogfeld an, Sie es effizienter finden vielleicht, verwenden Sie das Dialogfeld-Editor, um das Dialogfeld-Steuerelemente hinzufügen und anschließend die Steuerelemente Membervariablen zu implementieren.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>Hinzufügen eine Membervariablen für Dialogfeldsteuerelement in der Ressourcenansicht Verwendung mit dem Assistenten zum Hinzufügen von Member  
  
1.  Erweitern Sie in der Ressourcenansicht den Projektknoten, und das Dialogfeld-Knoten, um die Liste der Dialogfelder des Projekts anzuzeigen.  
  
2.  Doppelklicken Sie auf das Dialogfeld, zu dem Sie die Membervariable, um sie im Dialog-Editor Öffnen hinzufügen möchten.  
  
3.  Im Dialogfeld im Dialog-Editor angezeigt mit der rechten Maustaste des Steuerelements, zu dem Sie die Membervariable hinzufügen möchten.  
  
4.  Klicken Sie im Kontextmenü auf **Variable hinzufügen** zum Anzeigen der [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md).  
  
    > [!NOTE]
    >  Ein Standardwert ist bereits im bereitgestellt **Kontroll-ID**.  
  
5.  Geben Sie die Informationen in den Dialogfeldern des entsprechenden Assistenten. Finden Sie unter [Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md) für Weitere Informationen.  
  
6.  Klicken Sie auf **Fertig stellen** auf das Projekt der Definition und Implementierung Code hinzu, und schließen Sie den Assistenten.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>So fügen Sie eine Membervariable aus Klassenansicht Verwendung mit dem Assistenten zum Hinzufügen von Member hinzu  
  
1.  In [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), erweitern Sie den Projektknoten, um die Klassen im Projekt anzuzeigen.  
  
2.  Mit der rechten Maustaste in der Klasse, zu der Sie eine Variable hinzufügen möchten.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Variable hinzufügen** den Assistenten zum Hinzufügen von Member angezeigt.  
  
4.  Geben Sie die Informationen in den Dialogfeldern des entsprechenden Assistenten. Finden Sie unter [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) Details.  
  
5.  Klicken Sie auf **Fertig stellen** auf das Projekt der Definition und Implementierung Code hinzu, und schließen Sie den Assistenten.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)