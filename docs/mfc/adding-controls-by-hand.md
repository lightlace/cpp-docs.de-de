---
title: Hinzufügen von Steuerelementen von Hand | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efe510c4376255c24470a799b5dde17021894bf0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-controls-by-hand"></a>Manuelles Hinzufügen von Steuerelementen
Sie können entweder [Hinzufügen von Steuerelementen zu einem Dialogfeld mit dem Dialog-Editor](../mfc/using-the-dialog-editor-to-add-controls.md) oder fügen Sie sie selbst, mit dem Code.  
  
 Um ein Steuerelementobjekt selbst erstellen, werden Sie in der Regel die C++-Control-Objekt in einem C++-Dialog oder Rahmenfensterobjekt einbetten. Wie viele andere Objekte im Framework erfordern Steuerelemente zweistufige Konstruktion. Rufen Sie des Steuerelements **erstellen** Memberfunktion als Teil der Erstellung des übergeordneten Dialogfeld Feld oder den Frame-Fensters. Für Dialogfelder, dies erfolgt normalerweise [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), und für den Rahmenfenstern werden in [OnCreate](../mfc/reference/cwnd-class.md#oncreate).  
  
 Das folgende Beispiel zeigt, wie Sie deklarieren, können eine `CEdit` Objekt in der Klassendeklaration von einer abgeleiteten Dialogfeldklasse, und rufen Sie anschließend die **erstellen** Memberfunktion in `OnInitDialog`. Da die `CEdit` Objekt als eingebettetes Objekt deklariert wird, es wird automatisch erstellt, wenn das Dialogfeldobjekt erstellt wird, jedoch mit einem eigenen noch initialisiert werden muss **erstellen** Memberfunktion.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]  
  
 Die folgenden `OnInitDialog` Funktion richtet ein Rechteck ruft dann **erstellen** zum Erstellen von Windows-Bearbeitungssteuerelements und fügen Sie es an den nicht initialisierten `CEdit` Objekt.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]  
  
 Nach dem Erstellen des Objekts bearbeiten, können Sie auch den Eingabefokus auf das Steuerelement festlegen, durch Aufrufen der `SetFocus` Memberfunktion. Schließlich Sie 0 aus zurückgeben `OnInitDialog` anzuzeigen, das der Fokus festgelegt werden. Wenn Sie einen Wert ungleich NULL zurückgeben, wird vom Dialogfeld-Manager den Fokus auf das erste Steuerelement ein Element in der Liste der Dialogfeld-Element. In den meisten Fällen sollten Sie das Hinzufügen von Steuerelementen in den Dialogfeldern mit dem Dialog-Editor.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)   
 [CDialog::](../mfc/reference/cdialog-class.md#oninitdialog)

