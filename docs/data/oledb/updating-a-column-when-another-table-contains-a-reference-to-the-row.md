---
title: "Aktualisieren einer Spalte, wenn eine andere Tabelle einen Verweis auf die Zeile enth&#228;lt | Microsoft Docs"
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
  - "Rowsets, Spaltenaktualisierungen"
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Aktualisieren einer Spalte, wenn eine andere Tabelle einen Verweis auf die Zeile enth&#228;lt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einige Anbieter können erkennen, welche Spalten in der Zeile geändert wurden, viele Anbieter können dies jedoch nicht.  Daher kann das Aktualisieren einer Spalte zu einer Fehlermeldung führen, wenn es einen Verweis auf die Zeile gibt, die Sie aktualisieren möchten.  Erstellen Sie zur Lösung dieses Problems einen separaten Accessor, der nur die zu ändernden Spalten enthält.  Leiten Sie die Nummer dieses Accessors an `SetData` weiter.  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)