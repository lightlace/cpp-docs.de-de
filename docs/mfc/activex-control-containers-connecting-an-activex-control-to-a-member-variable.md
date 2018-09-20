---
title: 'ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae0cefa518ce44913f5c316a096d221fa9bd41aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433854"
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

