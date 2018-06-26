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
ms.openlocfilehash: b3aa243ab8c0fb49e20e5b7485acdcd8bb808831
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930467"
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
  
     Beispielsweise *M_circctl*.  
  
6.  Klicken Sie auf **Fertig stellen** , akzeptieren Sie Ihre Auswahl, und beenden den Assistenten zum Hinzufügen von Member.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

