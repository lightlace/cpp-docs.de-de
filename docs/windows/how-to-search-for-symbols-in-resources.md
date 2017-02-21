---
title: "How to: Search for Symbols in Resources | Microsoft Docs"
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
  - "symbols, finding"
  - "resources [Visual Studio], searching for symbols"
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# How to: Search for Symbols in Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So suchen Sie Symbole in Ressourcen  
  
1.  Wählen Sie im Menü **Bearbeiten** den Befehl **Symbol suchen**.  
  
2.  Wählen Sie im Dialogfeld [Symbol suchen](assetId:///63e93d9c-784f-418d-a76a-723da5ff5d96) aus der Dropdownliste im Feld **Suchen nach** einen früheren Suchbegriff aus, oder geben Sie die zu suchende Zugriffstaste ein \(z. B. ID\_ACCEL1\).  
  
    > [!TIP]
    >  Um [reguläre Ausdrücke](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md) für die Suche zu verwenden, müssen Sie im Menü **Bearbeiten** den [Befehl „Suche in Dateien“](../Topic/Find%20Command.md) anstelle des Befehls **Symbol suchen** verwenden.  Damit reguläre Ausdrücke aktiviert werden, müssen Sie das Kontrollkästchen **Reguläre Ausdrücke verwenden** im [Dialogfeld „Suchen“](assetId:///dad03582-4931-4893-83ba-84b37f5b1600) aktivieren.  Klicken Sie dann rechts neben dem Feld **Suchen nach** auf den PFEIL\-NACH\-RECHTS, um eine Liste von regulären Suchausdrücken aufzurufen.  Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im Feld **Suchen nach** angezeigt.  
  
3.  Wählen Sie beliebige **Such**\-Optionen aus.  
  
4.  Klicken Sie auf **Weitersuchen**.  
  
    > [!NOTE]
    >  Die Suche nach Symbolen in Zeichenfolgen\-, Zugriffstasten\- oder Binärressourcen wird nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)