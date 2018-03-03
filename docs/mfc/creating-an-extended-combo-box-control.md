---
title: Erstellen eines erweiterten Kombinationsfeld-Steuerelements | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80c3dc06ff391d1a90342f867813f60f9ce85bd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-extended-combo-box-control"></a>Erstellen eines erweiterten Kombinationsfeld-Steuerelements
Wie die erweiterten Kombinationsfeld-Steuerelement erstellt wird, hängt davon ab, ob das Steuerelement in einem Dialogfeld verwendet oder in einem nicht-Dialogfenster-Fenster.  
  
### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>Verwenden von CComboBoxEx direkt in einem Dialogfeld  
  
1.  Der Dialog-Editor die Dialogfeldvorlagen-Ressource hinzufügen einer erweiterten Kombinationsfeld-Steuerelement. Geben Sie die Steuerelement-ID.  
  
2.  Geben Sie alle Formate, die erforderlich sind, mithilfe des Dialogfelds "Eigenschaften" des erweiterten Kombinationsfeld-Steuerelements.  
  
3.  Verwenden der [Assistenten zum Hinzufügen von Variablen](../ide/adding-a-member-variable-visual-cpp.md) eine Membervariable des Typs hinzufügen [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) mit der Eigenschaft des Steuerelements. Können Sie bei diesem Member Aufrufen `CComboBoxEx` Memberfunktionen.  
  
4.  Verwenden des Eigenschaftenfensters Handlerfunktionen in Dialogklasse für alle erweiterten Kombinationsfeld Feld benachrichtigungsmeldungen zuordnen behandelt werden müssen (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie ggf. Weitere Formate für die `CComboBoxEx` Objekt.  
  
### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>Verwenden von CComboBoxEx in einem Dialogfenster  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.  
  
2.  Rufen Sie das Steuerelement [erstellen](../mfc/reference/ctabctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so früh wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handlerfunktion. Legen Sie die Formate für das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

