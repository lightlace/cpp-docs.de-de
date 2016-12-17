---
title: "How to: Create a Resource Script File"
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
  - "rc files, creating"
  - ".rc files, creating"
  - "resource script files, creating"
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Create a Resource Script File
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der Ressourcen\-Editor ist in Express\-Editionen nicht verfügbar.  
>   
>  Diese Materialien beziehen sich auf Windows\-Desktopanwendungen. Für Projekte in .NET\-Sprachen werden keine Ressourcenskriptdateien verwendet. Weitere Informationen finden Sie unter [Ressourcendateien](../mfc/resource-files-visual-studio.md).  
  
### So erstellen Sie eine neue Ressourcenskriptdatei \(RC\-Datei\)  
  
1.  Verschieben Sie den Fokus auf den vorhandenen Projektordner im `Solution Explorer`, z. B. "MyProject".  
  
    > [!NOTE]
    >  Verwechseln Sie den Projektordner nicht mit dem Projektmappenordner im Projektmappen\-Explorer. Wenn Sie den Fokus auf den Projektmappenordner verschieben, werden im Dialogfeld **Neues Element hinzufügen** \(unter Schritt 3\) andere Optionen angezeigt.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf den Ordner **Visual C\+\+**, und wählen Sie dann **Ressourcendatei \(.rc\)** im rechten Bereich aus.  
  
4.  Geben Sie im Textfeld **Name** einen Namen für die Ressourcenskriptdatei ein, und klicken Sie dann auf **Öffnen**.  
  
 Sie können jetzt neue Ressourcen [erstellen](../windows/how-to-create-a-resource.md) und diese der RC\-Datei hinzufügen.  
  
> [!NOTE]
>  Eine Ressourcenskriptdatei \(.rc\) kann nur in ein vorhandenes Projekt aufgenommen werden, das bereits in der Visual Studio\-IDE geladen wurde. Es können keine eigenständige RC\-Datei \(außerhalb des Projekts\) erstellt werden.[Ressourcenvorlagen](../windows/how-to-use-resource-templates.md) \(RCT\-Dateien\) können jederzeit erstellt werden.  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)