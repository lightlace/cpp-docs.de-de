---
title: Erstellen des Monatskalender-Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f55960177fa8bc9a31ebfd16b4dbc6aeaba3ee38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-month-calendar-control"></a>Erstellen des Monatskalender-Steuerelements
Wie im Monatskalender-Steuerelement erstellt wird, hängt davon ab, ob das Steuerelement in einem Dialogfeld verwendet oder in einem nicht-Dialogfenster-Fenster.  
  
### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>Verwenden von CMonthCalCtrl direkt in einem Dialogfeld  
  
1.  Der Dialog-Editor wird der Dialogfeldvorlagen-Ressource ein Monatskalender-Steuerelement hinzugefügt. Geben Sie die Steuerelement-ID.  
  
2.  Geben Sie alle Formate, die erforderlich sind, über das Dialogfeld "Eigenschaften", der im Monatskalender-Steuerelement.  
  
3.  Verwenden der [Assistenten zum Hinzufügen von Variablen](../ide/adding-a-member-variable-visual-cpp.md) eine Membervariable des Typs hinzufügen [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) mit der Eigenschaft des Steuerelements. Können Sie bei diesem Member Aufrufen `CMonthCalCtrl` Memberfunktionen.  
  
4.  Verwendet im Eigenschaftenfenster Handlerfunktionen in Dialogklasse zuordnen, für die Month Calendar-Steuerelement Benachrichtigungen angezeigt werden, behandeln müssen (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie ggf. Weitere Formate für die `CMonthCalCtrl` Objekt.  
  
### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Verwenden von CMonthCalCtrl in einem Dialogfenster  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.  
  
2.  Rufen Sie das Steuerelement [erstellen](../mfc/reference/cmonthcalctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so früh wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handlerfunktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

