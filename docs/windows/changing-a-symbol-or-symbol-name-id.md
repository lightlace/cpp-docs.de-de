---
title: "Changing a Symbol or Symbol Name (ID) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Changing a Symbol or Symbol Name (ID)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine neue Ressource oder ein Ressourcenobjekt erstellen, weist die Entwicklungsumgebung einen standardmäßigen Symbolnamen zu, beispielsweise IDD\_DIALOG1.  Sie können das Fenster [Eigenschaften](../Topic/Properties%20Window.md) verwenden, um den standardmäßigen Symbolnamen zu ändern oder um den Namen jedes mit einer Ressource verknüpften Symbols zu ändern.  
  
### So ändern Sie den Symbolname einer Ressource  
  
1.  Wählen Sie die Ressource in der [Ressourcenansicht](../windows/resource-view-window.md) aus.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Geben Sie im Fenster **Eigenschaften** einen neuen Symbolnamen ein, oder wählen Sie einen aus der Liste der vorhandenen Symbole im Feld **ID** aus.  
  
     Wenn Sie einen neuen Symbolnamen eingeben, wird diesem automatisch ein Wert zugewiesen.  
  
 Sie können das Dialogfeld [Ressourcensymbole](../windows/resource-symbols-dialog-box.md) verwenden, um die Namen der zurzeit nicht einer Ressource zugewiesenen Symbole zu ändern.  Weitere Informationen finden Sie unter [Ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)