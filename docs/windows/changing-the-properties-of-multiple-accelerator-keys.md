---
title: "Changing the Properties of Multiple Accelerator Keys | Microsoft Docs"
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
  - "keyboard shortcuts [C++], property changing"
  - "accelerator tables [C++], changing properties"
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Changing the Properties of Multiple Accelerator Keys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So ändern Sie die Eigenschaften mehrerer Zugriffstasten  
  
1.  Öffnen Sie die Zugriffstastentabelle, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md) auf das zugehörige Symbol doppelklicken.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Markieren Sie die gewünschten Zugriffstasten, indem Sie STRG gedrückt halten, während Sie auf die einzelnen Elemente klicken.  
  
3.  Wechseln Sie zum [Eigenschaftenfenster](../Topic/Properties%20Window.md), und geben Sie die Werte ein, die von allen ausgewählten Zugriffstasten gemeinsam genutzt werden sollen.  
  
    > [!NOTE]
    >  Jeder Modifiziererwert wird als boolesche Eigenschaft im Eigenschaftenfenster angezeigt.  Wenn Sie den Wert eines [Modifizierers](../windows/accelerator-modifier-property.md) im Eigenschaftenfenster ändern, wird der neue Modifizierer von der Zugriffstastentabelle als Ergänzung zu anderen Modifizierern behandelt, die bereits vorhanden waren.  Daher müssen Sie beim Festlegen von Modifiziererwerten alle Modifizierer berücksichtigen, um sicherzustellen, dass alle Zugriffstasten dieselben Modifizierereinstellungen verwenden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Editing Accelerator Tables](../windows/editing-accelerator-tables.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)