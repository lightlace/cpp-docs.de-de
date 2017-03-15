---
title: "Changing the Names of Symbol Header Files | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing.header"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource files, multiple"
  - "Resource Includes dialog box"
  - "symbol header files, changing names"
  - "symbol header files"
  - "header files, changing names"
  - "names [C++], symbol header files"
  - "symbols, symbol header files"
  - "Resource.h"
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Changing the Names of Symbol Header Files
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Normalerweise werden alle Symboldefinitionen in der Datei Resource.h gespeichert.  Jedoch müssen Sie den Namen dieser Includedatei möglicherweise ändern, sodass Sie z. B. mit mehr als eine Ressourcendatei im selben Verzeichnis arbeiten können.  
  
### So ändern Sie den Namen den Symbolheaderdatei für die Ressource  
  
1.  Klicken Sie mit der rechten Maustaste in der [Ressourcenansicht](../windows/resource-view-window.md) auf die RC\-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Geben Sie in der **Symbolheaderdatei** den neuen Namen für die Includedatei ein.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.*  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)