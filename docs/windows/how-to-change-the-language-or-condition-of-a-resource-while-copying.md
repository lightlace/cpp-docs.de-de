---
title: "How to: Change the Language or Condition of a Resource While Copying"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Language property"
  - "condition property of resource"
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Change the Language or Condition of a Resource While Copying
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Kopieren in eine Ressource können Sie ihre Sprachen\- und\/oder Bedingungseigenschaft ändern.  
  
-   Die Ressourcensprache ermittelt lediglich die Sprache für die Ressource.  Diese wird von [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) verwendet, um die gewünschte Ressource zu ermitteln.  \(Ressourcen können für jede Sprache Unterschiede aufweisen, die nicht mit dem Text zusammenhängen, z. B. Tastenkombinationen, die nur auf einer japanischen Tastatur funktionieren, oder eine Bitmap, die nur für Builds in Chinesisch gilt usw.\)  
  
-   Die Bedingung einer Ressource stellt ein definiertes Symbol dar, das eine Bedingung angibt, unter der diese bestimmte Ressourcenkopie zu verwenden ist.  
  
 Sprache und Bedingung einer Ressource werden im Arbeitsbereichsfenster nach dem Ressourcennamen in Klammern angezeigt.  In diesem Beispiel verwendet die Ressource mit dem Namen „IDD\_AboutBox“ Finnisch als Sprache und „XX33“ als Bedingung.  
  
```  
IDD_AboutBox (Finnish – XX33)  
```  
  
### So kopieren Sie eine vorhandene Ressource und ändern die Sprache oder Bedingung  
  
1.  Klicken Sie in der RC\-Datei oder im Fenster [Ressourcenansicht](../windows/resource-view-window.md) mit der rechten Maustaste auf die Ressource, die Sie kopieren möchten.  
  
2.  Wählen Sie im Kontextmenü **Kopie einfügen** aus.  
  
3.  Führen Sie im Dialogfeld **Ressourcenkopie einfügen** die folgenden Aktionen durch:  
  
    -   Wählen Sie im Listenfeld **Sprache** die gewünschte Sprache aus.  
  
    -   Geben Sie im Feld **Bedingung** die gewünschte Bedingung ein.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [How to: Copy Resources](../windows/how-to-copy-resources.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)