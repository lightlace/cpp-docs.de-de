---
title: Erstellen die Datums- und Zeitauswahl Steuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce7c987bf1284d0287cd0206572209d7ae2d0b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342133"
---
# <a name="creating-the-date-and-time-picker-control"></a>Erstellen des Steuerelements für Datum und Uhrzeit
Wie die Datums- / Zeitauswahl-Steuerelement erstellt wird, hängt davon ab, ob das Steuerelement in einem Dialogfeld verwendet oder in einem nicht-Dialogfenster-Fenster.  
  
### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>Verwenden von CDateTimeCtrl direkt in einem Dialogfeld  
  
1.  Der Dialog-Editor fügen Sie ein Datum und Uhrzeit die Datumsauswahl hinzu der Dialogfeldvorlagen-Ressource ein. Geben Sie die Steuerelement-ID.  
  
2.  Geben Sie alle erforderlichen Formate mithilfe des Dialogfelds "Eigenschaften" für die Datums- / Zeitauswahl-Steuerelement.  
  
3.  Verwenden der [Assistenten zum Hinzufügen von Variablen](../ide/adding-a-member-variable-visual-cpp.md) eine Membervariable des Typs hinzufügen [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) mit der Eigenschaft des Steuerelements. Können Sie bei diesem Member Aufrufen `CDateTimeCtrl` Memberfunktionen.  
  
4.  Verwenden des Eigenschaftenfensters Handlerfunktionen in Dialogklasse für alle Datums-/ Zeitauswahl-Steuerelement zuordnen [Benachrichtigung](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) Nachrichten, die Sie behandeln müssen (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie ggf. Weitere Formate für die `CDateTimeCtrl` Objekt.  
  
### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Verwenden von CDateTimeCtrl in einem Dialogfenster  
  
1.  Deklarieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.  
  
2.  Rufen Sie das Steuerelement [erstellen](../mfc/reference/ctabctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so früh wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handlerfunktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

