---
title: Erstellen des Registersteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
dev_langs:
- C++
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3945d441130d723bbda3d137f2adae637d56c2b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344090"
---
# <a name="creating-the-tab-control"></a>Erstellen des Registersteuerelements
Wie das Registerkarten-Steuerelement erstellt wird, hängt davon ab, ob das Steuerelement in einem Dialogfeld verwendet oder in einem nicht-Dialogfenster-Fenster.  
  
### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>Verwenden von CTabCtrl direkt in einem Dialogfeld  
  
1.  Der Dialog-Editor wird der Dialogfeldvorlagen-Ressource ein Registerkarten-Steuerelement hinzugefügt. Geben Sie die Steuerelement-ID.  
  
2.  Verwenden der [Assistenten zum Hinzufügen von Variablen](../ide/adding-a-member-variable-visual-cpp.md) eine Membervariable des Typs hinzufügen [CTabCtrl](../mfc/reference/ctabctrl-class.md) mit der Eigenschaft des Steuerelements. Können Sie bei diesem Member Aufrufen `CTabCtrl` Memberfunktionen.  
  
3.  Ordnen Sie Handlerfunktionen in Dialogklasse für alle benachrichtigungsmeldungen des Registersteuerelements, die Sie behandeln müssen. Weitere Informationen finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
4.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie die Formate für die `CTabCtrl`.  
  
### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>Verwenden von CTabCtrl in einem Dialogfenster  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.  
  
2.  Rufen Sie das Steuerelement [erstellen](../mfc/reference/ctabctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so früh wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handlerfunktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.  
  
 Nach der `CTabCtrl` Objekt erstellt wurde, können Sie festlegen, oder deaktivieren Sie die folgenden erweiterten Formate:  
  
-   **TCS_EX_FLATSEPARATORS** das Registerkarten-Steuerelement wird als Trennzeichen zwischen den Registerkartenelementen gezeichnet. Diese erweiterten Stil nur wirkt sich auf Steuerelemente Registerkarte, die über die **TCS_BUTTONS-Format** und **TCS_FLATBUTTONS** Stile. Standardmäßig erstellt das Registerkarten-Steuerelement mit dem **TCS_FLATBUTTONS** Stil Hiermit erweiterter Stil.  
  
-   **TCS_EX_REGISTERDROP** generiert das Registerkarten-Steuerelement **TCN_GETOBJECT** benachrichtigungsmeldungen Ablageziel anfordern Objekts, wenn Sie ein Objekt über die Registerkarte "-Elemente im Steuerelement gezogen wird.  
  
    > [!NOTE]
    >  Zum Empfangen der **TCN_GETOBJECT** Benachrichtigung, müssen Sie die OLE-Bibliotheken mit einem Aufruf von initialisieren [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit).  
  
 Diese Stile abgerufen und festgelegt werden, nachdem das Steuerelement erstellt wurde, mit der entsprechenden Aufrufe an die [entsprechenden Memberfunktionen GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) und [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) Memberfunktionen.  
  
 Legen Sie z. B. die **TCS_EX_FLATSEPARATORS** Stil mit der folgenden Codezeilen:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]  
  
 Deaktivieren der **TCS_EX_FLATSEPARATORS** Formats mit einem `CTabCtrl` Objekt mit den folgenden Codezeilen:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]  
  
 Dadurch werden die Trennzeichen, die zwischen den Schaltflächen des auftreten entfernt die `CTabCtrl` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

