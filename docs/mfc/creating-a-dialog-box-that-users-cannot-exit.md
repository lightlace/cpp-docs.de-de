---
title: "Creating a Dialog Box That Users Cannot Exit"
ms.custom: na
ms.date: "12/14/2016"
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
  - "dialog boxes, creating"
  - "modal dialog boxes, logon screens"
  - "logon screens"
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Dialog Box That Users Cannot Exit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können ein Laufzeitdialogfeld erstellen, das von Benutzern nicht beendet werden kann. Diese Art Dialogfeld ist nützlich für Anmeldungen und für Sperren von Anwendungen oder Dokumenten.  
  
### So erstellen Sie ein Dialogfeld, das von Benutzern nicht beendet werden kann  
  
1.  Legen Sie im Abschnitt **Eigenschaften** des Dialogfelds die Eigenschaft **Systemmenü** auf **falsch** fest.  
  
     Dadurch werden das Systemmenü des Dialogfelds und die Schaltfläche **Schließen** deaktiviert.  
  
2.  Löschen Sie auf dem Formular des Dialogfelds die Schaltflächen **Abbrechen** und **OK**.  
  
     Zur Laufzeit kann ein Benutzer ein modales Dialogfeld, das diese Eigenschaften aufweist, nicht beenden.  
  
 Um das Testen dieser Art von Dialogfeldern zu ermöglichen, erkennt die Funktion zum Testen von Dialogfeldern, wenn ESC gedrückt wird. \(ESC wird auch als virtuelle Taste „VK\_ESCAPE“ bezeichnet.\) Unabhängig davon, wie das Laufzeitverhalten des Dialogfelds ausgelegt wurde, im Testmodus können Sie es durch Drücken von ESC beenden.  
  
> [!NOTE]
>  Um bei MFC\-Anwendungen ein Dialogfeld zu erstellen, das von Benutzern nicht beendet werden kann, müssen Sie das Standardverhalten von `OnOK`und `OnCancel` außer Kraft setzen, denn selbst wenn Sie die zugeordneten Schaltflächen löschen, kann das Dialogfeld immer noch durch Drücken von EINGABETASTE oder ESC geschlossen werden.  
  
 Informationen über das Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop\-Apps](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)