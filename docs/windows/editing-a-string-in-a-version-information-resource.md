---
title: "Editing a String in a Version Information Resource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version information resources"
  - "resources [Visual Studio], editing version information"
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Editing a String in a Version Information Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So bearbeiten Sie eine Zeichenfolge in einer Versionsinformationsressource  
  
1.  Klicken Sie ein Mal auf das Element, um es auszuwählen, und dann noch ein Mal, um mit der Bearbeitung zu beginnen. Nehmen Sie die Änderungen direkt in der Versionsinformationstabelle oder im [Eigenschaftenfenster](../Topic/Properties%20Window.md) vor. Die vorgenommenen Änderungen werden an beiden Orten berücksichtigt.  
  
     **Hinweis** Beim Bearbeiten des **FILEFLAGS**\-Schlüssels im Versionsinformations\-Editor werden Sie bemerken, dass Sie die Eigenschaften **Debug**, **Private Build** oder **Special Build** \(im Eigenschaftenfenster\) für RC\-Dateien nicht festlegen können:  
  
    -   Der Versionsinformations\-Editor legt die Eigenschaft **Debug** mit einer \#ifdef\-Direktive im Ressourcenskript fest, basierend auf dem **\_DEBUG**\-Build\-Flag.  
  
    -   Wenn für den **Private Build**\-Schlüssel ein **Wert** in der Versionsinformationstabelle festgelegt ist, ist die entsprechende **Private Build**\-Eigenschaft \(im Eigenschaftenfenster\) für den **FILEFLAGS**\-Schlüssel auf **True** festgelegt. Wenn der **Wert** leer ist, ist die Eigenschaft **False**. Analog dazu ist der **Special Build**\-Schlüssel \(in der Versionsinformationstabelle\) an die **Special Build**\-Eigenschaft für den **FILEFLAGS**\-Schlüssel gebunden.  
  
 Sie können die Informationssequenz des Zeichenfolgenblocks sortieren, indem Sie entweder auf den Spaltenkopf „Schlüssel“ oder den Spaltenkopf „Wert“ klicken. Mithilfe dieser Überschriften können die Informationen automatisch in der ausgewählten Reihenfolge neu angeordnet werden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [Versionsinformationen \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)