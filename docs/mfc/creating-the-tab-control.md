---
title: Erstellen des Registersteuerelements
ms.date: 11/04/2016
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
ms.openlocfilehash: 4627009e2e07d1c5692d83d8d6262a9fcd37977e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241961"
---
# <a name="creating-the-tab-control"></a>Erstellen des Registersteuerelements

Wie das Registerkarten-Steuerelement erstellt wird, hängt davon ab, ob Sie mithilfe des Steuerelements in einem Dialogfeld oder erstellen es in einer nicht-Dialogfenster.

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>Verwenden von CTabCtrl direkt in einem Dialogfeld

1. Der Dialog-Editor fügen Sie ein Registerkarten-Steuerelement hinzu, um der Dialogfeldvorlagen-Ressource. Geben Sie die Steuerelement-ID.

1. Verwenden der [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md) zum Hinzufügen einer Membervariablen des Typs [CTabCtrl](../mfc/reference/ctabctrl-class.md) mit der Eigenschaft des Steuerelements. Sie können diesen Member Aufrufen `CTabCtrl` Memberfunktionen.

1. Ordnen Sie Handlerfunktionen in die Dialogfeldklasse für alle benachrichtigungsmeldungen des Registersteuerelements, die Sie behandeln müssen. Weitere Informationen finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie die Formate für die `CTabCtrl`.

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>Zum Verwenden von CTabCtrl in einem nicht-Dialogfenster

1. Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.

1. Aufrufen des Steuerelements [erstellen](../mfc/reference/ctabctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so frühzeitig wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler-Funktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.

Nach der `CTabCtrl` Objekt erstellt wurde, können Sie festlegen oder löschen Sie die folgende erweiterte Stile:

- **TCS_EX_FLATSEPARATORS** das Registerkarten-Steuerelement wird Trennzeichen zwischen den Registerkartenelementen gezeichnet. Diese erweiterten Stil nur wirkt sich auf Steuerelemente Registerkarte, die die **TCS_BUTTONS-Format** und **TCS_FLATBUTTONS** Stile. Erstellen Sie in der Standardeinstellung das Registerkarten-Steuerelement mit dem **TCS_FLATBUTTONS** Stil legt dieser erweiterten Stil.

- **TCS_EX_REGISTERDROP** generiert das Registerkarten-Steuerelement **TCN_GETOBJECT** Objekt benachrichtigungsmeldungen an das Ziel eines Ablegevorgangs anfordern, wenn ein Objekt über die Registerkarte "-Elemente im Steuerelement gezogen wird.

    > [!NOTE]
    >  Zum Empfangen der **TCN_GETOBJECT** Benachrichtigung müssen Sie die OLE-Bibliotheken mit einem Aufruf von initialisieren [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit).

Diese Stile können abgerufen und festgelegt, nachdem das Steuerelement, mit entsprechenden aufrufen erstellt wurde der [entsprechenden Memberfunktionen GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) und [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) Memberfunktionen.

Legen Sie z. B. die **TCS_EX_FLATSEPARATORS** Stil mit den folgenden Codezeilen:

[!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]

Deaktivieren der **TCS_EX_FLATSEPARATORS** Formats mit einer `CTabCtrl` Objekt mit den folgenden Codezeilen:

[!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]

Hiermit werden die Trennzeichen, die zwischen den Schaltflächen der angezeigt werden. Ihre `CTabCtrl` Objekt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
