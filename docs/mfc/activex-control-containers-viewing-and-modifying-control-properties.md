---
title: "ActiveX-Steuerelementcontainer: Anzeigen und &#196;ndern von Steuerelementeigenschaften"
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
  - "ActiveX-Steuerelementcontainer [C++], Anzeigen und Ändern von Eigenschaften"
  - "ActiveX-Steuerelemente [C++], Eigenschaften"
  - "Steuerelemente [MFC], Eigenschaften"
  - "Eigenschaften [MFC], Anzeigen und Ändern"
  - "Ressourcen-Editoren, Anzeigen und Ändern von ActiveX-Steuerelementen"
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelementcontainer: Anzeigen und &#196;ndern von Steuerelementeigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein ActiveX\-Steuerelement in ein Projekt einfügen, ist es hilfreich, die Eigenschaften anzuzeigen und zu ändern, die das ActiveX\-Steuerelement unterstützt werden.  Dieser Artikel wird erläutert, wie der Visual C\+\+\-Ressourcen\-Editor verwendet, um dazu.  
  
 Wenn die ActiveX\-Steuerelement\-Containeranwendungsverwendung Steuerelemente zum Einbetten, können Sie die Eigenschaften des Steuerelements anzeigen und ändern während im Ressourcen\-Editor.  Sie können den Ressourcen\-Editor auch verwenden, um Eigenschaftswerte zur Entwurfszeit festzulegen.  Der Ressourcen\-Editor dann speichert automatisch diese Werte in der Ressourcendatei des Projekts.  Jede Instanz des Steuerelements verfügt dessen Eigenschaften, die mit diesen Werten initialisiert werden.  
  
 Diese Prozedur wird davon ausgegangen, dass ein Steuerelement in das Projekt eingefügt haben.  Weitere Informationen finden Sie unter [ActiveX\-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer\-Anwendung](../mfc/inserting-a-control-into-a-control-container-application.md).  
  
 Der erste Schritt, wenn die Eigenschaften des Steuerelements angezeigt wird, ist, um eine Instanz des Steuerelements der Dialogfeldvorlage des Projekts hinzufügen.  
  
### Um die Eigenschaften eines Steuerelements anzeigen  
  
1.  in der Ressourcenansicht öffnen Sie den Ordner **Dialogfeld**.  
  
2.  Öffnen Sie die Hauptdialogfeldvorlage.  
  
3.  Fügen Sie ein ActiveX\-Steuerelement mithilfe des Dialogfelds **ActiveX\-Steuerelement einfügen** ein.  Weitere Informationen finden Sie unter [ActiveX\-Steuerelemente zu einem Dialogfeld anzeigen und hinzufügen](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
4.  Wählen Sie das ActiveX\-Steuerelement im Dialogfeld aus.  
  
5.  Im Eigenschaftenfenster klicken Sie auf die Schaltfläche **Eigenschaften**.  
  
 Verwenden Sie das Dialogfeld **Eigenschaften**, um neue Eigenschaften gleichzeitig zu ändern und zu testen.  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)