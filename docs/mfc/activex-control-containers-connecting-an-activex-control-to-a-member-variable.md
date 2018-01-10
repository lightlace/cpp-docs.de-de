---
title: 'ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2248dd68b0ecc7471899552bcb7b0394f3f9f363
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

