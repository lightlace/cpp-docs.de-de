---
title: "ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelementcontainer [C++], Zugreifen auf ActiveX-Steuerelemente"
  - "ActiveX-Steuerelementcontainer [C++], ActiveX-Steuerelemente als Membervariablen"
  - "ActiveX-Steuerelemente [C++], Aufrufen"
  - "ActiveX-Steuerelemente [C++], Membervariablen des Projekte"
  - "Verbinden von ActiveX-Steuerelementen mit Containermembervariablen"
  - "Membervariablen [C++], ActiveX-Steuerelemente in Projekten"
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelementcontainer: Verbinden eines ActiveX-Steuerelements mit einer Membervariablen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die einfachste Möglichkeit, auf ein ActiveX\-Steuerelement aus der Steuerelementcontainer\-Anwendung zuzugreifen, wird das ActiveX\-Steuerelement mit eine Membervariable der Dialogfeldklasse zuzuordnen, die das Steuerelement enthält.  
  
> [!NOTE]
>  Dies ist nicht die einzige Möglichkeit, auf ein eingebettetes Steuerelement aus einer Containerklasse zugreifen, jedoch im Sinne dieses Artikels ist es ausreichend.  
  
### Hinzufügen einer Membervariablen die Dialogfeldklasse  
  
1.  In der Klassenansicht klicken Sie auf die Hauptdialogfeldklasse xxxx 2, um das Kontextmenü zu öffnen.  Beispielsweise `CContainerDlg`.  
  
2.  Klicken Sie im Kontextmenü **Hinzufügen** und dann auf **Variable hinzufügen**.  
  
3.  Im Assistenten zum Hinzufügen von Membervariablen klicken Sie auf **Steuerelementvariable**.  
  
4.  Im Listenfeld **Steuerelement\-ID** auf die Steuerelement\-ID des eingebetteten ActiveX\-Steuerelements aus.  Beispielsweise `IDC_CIRCCTRL1`.  
  
5.  Im Feld **Variablenname** geben Sie einen Namen ein.  
  
     Beispielsweise `m_circctl`.  
  
6.  Klicken Sie auf **Fertig stellen** , um die Auswahl zu akzeptieren und den Assistenten zum Hinzufügen von Membervariablen zu beenden.  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)