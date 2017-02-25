---
title: "DEFINE_COMMAND_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEFINE_COMMAND_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND_EX-Makro"
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DEFINE_COMMAND_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, wenn die [CCommand](../../data/oledb/ccommand-class.md)\-Klasse verwendet.  Stütz\-Unicode und ANSI\-Anwendungen.  
  
## Syntax  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### Parameter  
 *x*  
 \[in\] Der Name der Klasse des Benutzerdatensatzes \(Befehl\).  
  
 `wszCommand`  
 \[in\] die Befehlszeichenfolge, die verwendet wird, um das Rowset zu erstellen, wenn der [CCommand](../../data/oledb/ccommand-class.md) bereitgestellt werden.  
  
## Hinweise  
 Die Befehlszeichenfolge, die Sie angeben, wird als Standardwert verwendet, wenn Sie nicht der Befehlstext in [CCommand::Open](../../data/oledb/ccommand-open.md)\-Methode angeben.  
  
 Dieses Makro akzeptiert Unicode\-Zeichenfolgen, unabhängig vom Anwendungstyp.  Dieses Makro wird über [DEFINE\_COMMAND](../../data/oledb/define-command.md) bevorzugt, da Unicode und ANSI\-Anwendungen unterstützt.  
  
## Beispiel  
 Siehe [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)