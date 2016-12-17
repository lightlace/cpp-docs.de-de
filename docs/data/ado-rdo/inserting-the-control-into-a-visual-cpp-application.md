---
title: "Einf&#252;gen des Steuerelements in eine Visual&#160;C++-Anwendung"
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
  - "ActiveX-Steuerelemente [C++], Hinzufügen zu Dialogfeldern"
ms.assetid: 7d517735-057b-49e3-8edf-eb087369b5b9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Einf&#252;gen des Steuerelements in eine Visual&#160;C++-Anwendung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX\-Steuerelemente können über eine Symbolleiste oder mithilfe des Dialogfelds [ActiveX\-Steuerelement einfügen](../../mfc/insert-activex-control-dialog-box.md) in ein Dialogfeld eingefügt werden.  
  
### So fügen Sie ein ActiveX\-Steuerelement aus der Toolbox ein  
  
1.  Klicken Sie mit der rechten Maustaste auf einen leeren Bereich der Toolbox.  
  
2.  Klicken Sie im Kontextmenü auf **Toolbox anpassen**, und wählen Sie dann die gewünschten Steuerelemente aus.  
  
3.  Ziehen Sie die Steuerelemente in das Dialogfeld im Dialog\-Editor.  
  
### So fügen Sie ein ActiveX\-Steuerelement aus dem Dialog\-Editor ein  
  
1.  Klicken Sie mit der rechten Maustaste in das Dialogfeld.  
  
2.  Klicken Sie im Kontextmenü auf [ActiveX\-Steuerelement einfügen](../../mfc/insert-activex-control-dialog-box.md).  
  
    > [!NOTE]
    >  Wenn Sie ein ActiveX\-Steuerelement mithilfe von **ActiveX\-Steuerelement einfügen** in ein Projekt einfügen, werden keine [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md) in das Projekt aufgenommen.  Sie sind selbst dafür zuständig, eine Wrapperklasse zu erstellen, um die Steuerelementfunktionen anzupassen.  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)