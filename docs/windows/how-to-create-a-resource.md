---
title: "How to: Create a Resource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toolbars [C++], resources"
  - "resource toolbars"
  - "resources [Visual Studio], creating"
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# How to: Create a Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Die Ressourcenansicht wird in Express\-Editionen nicht unterstützt.  
  
### So erstellen Sie eine neue Ressource in der Ressourcenansicht  
  
1.  Klicken Sie, während sich der Fokus in der [Ressourcenansicht](../windows/resource-view-window.md) befindet, auf das Menü **Bearbeiten**, und wählen Sie **Ressource hinzufügen** aus \(oder klicken Sie mit der rechten Maustaste in der Ressourcenansicht auf die RC\-Datei, und wählen Sie im Kontextmenü den Befehl **Ressource hinzufügen** aus\).  
  
     **Hinweis** Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md) den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
### So erstellen Sie eine neue Ressource im Projektmappen\-Explorer  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektordner, und wählen Sie **Hinzufügen** aus. Klicken Sie dann im Kontextmenü auf **Ressource hinzufügen**.  
  
     Wenn im Projekt noch keine RC\-Datei vorhanden ist, wird mit diesem Schritt eine erstellt. Anschließend können Sie diesen Schritt wiederholen, um der neuen RC\-Datei spezifische Ressourcentypen hinzuzufügen.  
  
2.  Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md) den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
### So erstellen Sie eine neue Ressource in der Klassenansicht  
  
1.  Klicken Sie in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf die Klasse, und wählen Sie **Hinzufügen** aus. Klicken Sie dann im Kontextmenü auf **Ressource hinzufügen**.  
  
2.  Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md) den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
### So erstellen Sie eine neue Ressource über das Menü "Projekt"  
  
1.  Wählen Sie im Menü **Projekt** den Befehl **Ressource hinzufügen** aus.  
  
 Wenn Sie eine neue Ressource erstellen, wird der Ressource von Visual C\+\+ ein eindeutiger Name zugewiesen, z. B. "IDD\_Dialog1". Sie können diese Ressourcen\-ID anpassen, indem Sie die Ressourceneigenschaften entweder im zugehörigen Ressourcen\-Editor oder im [Eigenschaftenfenster](../Topic/Properties%20Window.md) bearbeiten.  
  
 Eine Ressource kann entweder als neue Standardressource \(die auf keiner Vorlage basiert\) oder als Ressource erstellt werden, die von einer [Vorlage](../windows/how-to-use-resource-templates.md) erstellt wurde.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.*  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)