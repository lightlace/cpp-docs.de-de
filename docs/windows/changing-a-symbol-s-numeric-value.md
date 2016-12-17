---
title: "Changing a Symbol&#39;s Numeric Value"
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
  - "vc.editors.symbol.changing.value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric values"
  - "symbols, numeric values"
  - "numeric values, changing symbols"
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Changing a Symbol&#39;s Numeric Value
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für mit einer einzelnen Ressource verknüpfte Symbole können Sie das Fenster [Eigenschaften](../Topic/Properties%20Window.md) verwenden, um den Symbolwert zu ändern.  Sie können das Dialogfeld [Ressourcensymbole](../windows/resource-symbols-dialog-box.md) verwenden, um den Wert der zurzeit nicht einer Ressource zugewiesenen Symbole zu ändern.  Weitere Informationen finden Sie unter [Ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).  
  
### So ändern Sie einen zu einer einzelnen Ressource oder einem Objekt zugewiesenen Symbolwert  
  
1.  Wählen Sie die Ressource in der [Ressourcenansicht](../windows/resource-view-window.md) aus.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Geben Sie im Fenster **Eigenschaften** den Symbolnamen, gefolgt von einem Gleichheitszeichen und eine Ganzzahl in das Feld **ID** ein, beispielsweise:  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 Der neue Wert wird in der Symbolheaderdatei gespeichert, wenn Sie das nächste Mal das Projekt speichern.  Nur der Symbolnamen verbleibt weiterhin im Feld „ID“ sichtbar. Nach der Überprüfung werden das Gleichheitszeichen und der Wert nicht mehr angezeigt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)