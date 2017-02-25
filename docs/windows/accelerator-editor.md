---
title: "Accelerator Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.accelerator.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator tables [C++], editing"
  - "tables [Visual Studio], accelerator key"
  - "accelerator keys"
  - "resource editors, Accelerator editor"
  - "keyboard shortcuts [C++], Accelerator editor"
  - "Accelerator editor"
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Accelerator Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Zugriffstastentabelle ist eine Windows\-Ressource, die eine Liste mit Zugriffstasten \(auch als Tastenkombinationen bezeichnet\) und die Befehlsbezeichner enthält, die ihnen zugeordnet sind. Ein Programm kann über mehrere Zugriffstastentabellen verfügen.  
  
 Normalerweise werden Zugriffstasten als Tastenkombinationen für Programmbefehle verwendet, die auch in einem Menü oder auf einer Symbolleiste verfügbar sind. Allerdings können Sie die Zugriffstastentabelle auch verwenden, um Tastenkombinationen für Befehle zu definieren, denen kein Objekt auf der Benutzeroberfläche zugeordnet ist.  
  
 Sie können die [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) verwenden, um Zugriffstastenbefehle mit Code zu verknüpfen.  
  
 Im Zugriffstasten\-Editor ist Folgendes möglich:  
  
-   [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)  
  
-   [Zuordnen einer Zugriffstaste zu einem Menüeintrag](../windows/associating-an-accelerator-key-with-a-menu-item.md)  
  
-   [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)  
  
-   [Verwenden vordefinierter Zugriffstasten](../windows/predefined-accelerator-keys.md)  
  
    > [!TIP]
    >  Im Zugriffstasten\-Editor können Sie mit der rechten Maustaste klicken, um ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.  
  
    > [!NOTE]
    >  Windows lässt die Erstellung leerer Zugriffstastentabellen nicht zu. Wenn Sie eine Zugriffstastentabelle ohne Einträge erstellen, wird diese beim Speichern automatisch gelöscht.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)