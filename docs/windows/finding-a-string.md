---
title: "Finding a String | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strings [C++], searching"
  - "strings [C++]"
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Finding a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine oder mehrere Zeichenfolgen in der Zeichenfolgentabelle suchen und den Befehl **Suche in Dateien** \(Menü **Bearbeiten**\) mit [regulären Ausdrücken](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md) verwenden, um alle Vorkommnisse von Zeichenfolgen zu finden, die die Kriterien des Mustervergleichs erfüllen.  
  
### So suchen Sie eine Zeichenfolge in der Zeichenfolgentabelle  
  
1.  Öffnen Sie die Zeichenfolgentabelle, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md) auf das zugehörige Symbol doppelklicken.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie im Menü **Bearbeiten** die Option **Suchen und Ersetzen** und anschließend **Suchen**.  
  
3.  Wählen Sie aus der Dropdownliste im Feld **Suchen nach** einen früheren Suchbegriff aus, oder geben Sie den Beschriftungstext oder Ressourcenbezeichner der gesuchten Zeichenfolge ein.  
  
4.  Wählen Sie beliebige Suchoptionen aus.  
  
5.  Klicken Sie auf **Weitersuchen**.  
  
    > [!TIP]
    >  Um beim Durchsuchen von Dateien reguläre Ausdrücke zu verwenden, wählen Sie den Befehl **Suche in Dateien** aus.  Geben Sie einen regulären Ausdruck für den Mustervergleich ein, oder klicken Sie rechts neben dem Feld **Suchen nach** auf die Schaltfläche, um eine Liste regulärer Suchausdrücke aufzurufen.  Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im Feld **Suchen nach** angezeigt.  Wenn Sie reguläre Ausdrücke verwenden, vergewissern Sie sich, dass das Kontrollkästchen **Mit: Reguläre Ausdrücke** aktiviert ist.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten \(die die Common Language Runtime zum Ziel haben\) finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [String Editor](../mfc/string-editor.md)   
 [Zeichenfolgen](_win32_Strings)   
 [Informationen zu Zeichenfolgen](_win32_About_Strings_cpp)