---
title: 'ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen | Microsoft Docs'
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
ms.openlocfilehash: 06a2b6a5ab17db7b512f1f44d2eda68169d71645
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen
Die einfachste Möglichkeit, ein ActiveX-Steuerelement aus, in dessen Steuerelementcontainer-Anwendung zuzugreifen ist, eine Membervariable der Dialogklasse, die das Steuerelement enthält das ActiveX-Steuerelement zugeordnet werden soll.  
  
> [!NOTE]
>  Dies ist nicht die einzige Möglichkeit, ein eingebettetes-Steuerelement in einem Container-Klasse zugreifen, aber im Rahmen dieses Artikels ist es ausreichend.  
  
### <a name="adding-a-member-variable-to-the-dialog-class"></a>Hinzufügen einer Membervariablen der Dialogfeld-Klasse  
  
1.  In der Klassenansicht mit der rechten Maustaste der Hauptdialogfeld-Klasse, um das Kontextmenü zu öffnen. Beispielsweise `CContainerDlg`.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen** und dann **Variable hinzufügen**.  
  
3.  Klicken Sie in der Variable Assistenten zum Hinzufügen, auf **Steuerelementvariable**.  
  
4.  In der **Kontroll-ID** Listenfeld, wählen Sie die Steuerelement-ID des eingebetteten ActiveX-Steuerelements. Beispielsweise `IDC_CIRCCTRL1`.  
  
5.  In der **Variablenname** Geben Sie einen Namen.  
  
     Beispielsweise `m_circctl`.  
  
6.  Klicken Sie auf **Fertig stellen** , akzeptieren Sie Ihre Auswahl, und beenden den Assistenten zum Hinzufügen von Member.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

