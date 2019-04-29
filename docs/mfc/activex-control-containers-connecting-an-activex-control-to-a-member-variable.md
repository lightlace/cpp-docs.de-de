---
title: 'ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
ms.openlocfilehash: c6bc063875f2a31c582c9de32e24e7dfbc7826c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394909"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen

Die einfachste Möglichkeit, ein ActiveX-Steuerelement aus, in dessen Steuerelementcontainer-Anwendung zugreifen muss das ActiveX-Steuerelement eine Membervariable der Dialogklasse zugeordnet, die das Steuerelement enthält.

> [!NOTE]
>  Dies ist nicht die einzige Möglichkeit, ein eingebettetes Steuerelement aus einer Container-Klasse zugreifen, aber für die Zwecke dieses Artikels reicht es aus.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>Hinzufügen einer Membervariablen auf die Dialogfeldklasse

1. In der Klassenansicht mit der rechten Maustaste die Hauptdialogfeldklasse, um das Kontextmenü zu öffnen. Beispielsweise `CContainerDlg`.

1. Klicken Sie im Kontextmenü auf **hinzufügen** und dann **Variable hinzufügen**.

1. Klicken Sie in der Variable Assistenten zum Hinzufügen, auf **Steuerungsvariable**.

1. In der **Steuerelement-ID** Listenfeld, wählen Sie die Steuerelement-ID des eingebetteten ActiveX-Steuerelements. Beispielsweise `IDC_CIRCCTRL1`.

1. In der **Variablenname** Geben Sie einen Namen.

   Z. B. *M_circctl*.

1. Klicken Sie auf **Fertig stellen** akzeptieren Ihre Auswahl, und beenden den Assistenten zum Hinzufügen von Membervariablen.

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)
