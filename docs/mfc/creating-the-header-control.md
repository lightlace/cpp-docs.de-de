---
title: Erstellen des Headersteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 465c880c480f9ccd3a52f6319ee97ed203c3bd74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344512"
---
# <a name="creating-the-header-control"></a>Erstellen des Headersteuerelements
Das Headersteuerelement ist nicht direkt im Dialog-Editor verfügbar sind, (obwohl Sie ein Listenfeld-Steuerelement, einschließlich dem Headersteuerelement hinzufügen können).  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>Um ein Headersteuerelement in einem Dialogfeld einfügen  
  
1.  Betten Sie eine Membervariable des Typs [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) in der Dialogfeldklasse.  
  
2.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)erstellen, und legen Sie die Formate für die `CHeaderCtrl`, positionieren Sie es, und zeigen Sie es.  
  
3.  Das Headersteuerelement Elemente hinzugefügt.  
  
4.  Verwendet Eigenschaftenfenster Handlerfunktionen in Dialogklasse zuordnen für Benachrichtigungen Headersteuerelements Nachrichten verarbeiten müssen (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Um ein Headersteuerelement in einer Ansicht (nicht in einer CListView) einfügen  
  
1.  Einbetten einer [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) Objekt in Ihrer Ansichtsklasse.  
  
2.  Formatieren, positionieren und die Header-Steuerelement-Fenster auch anzeigen, in der Ansicht [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Memberfunktion.  
  
3.  Das Headersteuerelement Elemente hinzugefügt.  
  
4.  Verwendet Eigenschaftenfenster Handlerfunktionen in Ansichtsklasse zuordnen für Benachrichtigungen Headersteuerelements Nachrichten verarbeiten müssen (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
 In beiden Fällen wird das eingebettete Steuerelement-Objekt erstellt, wenn das Objekt Ansichts- oder Dialogfeldobjekt erstellt wird. Sie aufrufen müssen [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md#create) um das Fenster des Steuerelements zu erstellen. Aufrufen, um das Steuerelement zu positionieren, [CHeaderCtrl:: Layout](../mfc/reference/cheaderctrl-class.md#layout) ursprüngliche Größe und Position des Steuerelements bestimmt und [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) auf die Position festgelegt werden sollen. Klicken Sie dann Elemente hinzufügen, wie in beschrieben [Hinzufügen von Elementen zum Headersteuerelement](../mfc/adding-items-to-the-header-control.md).  
  
 Weitere Informationen finden Sie unter [erstellen eine Headersteuerelements](http://msdn.microsoft.com/library/windows/desktop/bb775238) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

