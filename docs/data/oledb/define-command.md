---
title: "DEFINE_COMMAND"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "DEFINE_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND-Makro"
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, wenn die [CCommand](../../data/oledb/ccommand-class.md)\-Klasse verwendet.  Akzeptiert die nur Zeichenfolgentypen, die den angegebenen Anwendungstyp übereinstimmen \(ANSI oder Unicode\).  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) anstelle von `DEFINE_COMMAND` verwenden.  
  
## Syntax  
  
```  
  
DEFINE_COMMAND(  
x  
,   
szCommand  
 )  
  
```  
  
#### Parameter  
 *x*  
 \[in\] Der Name der Klasse des Benutzerdatensatzes \(Befehl\).  
  
 `szCommand`  
 \[in\] die Befehlszeichenfolge, die verwendet wird, um das Rowset zu erstellen, wenn der [CCommand](../../data/oledb/ccommand-class.md) bereitgestellt werden.  
  
## Hinweise  
 Die Befehlszeichenfolge, die Sie angeben, wird als Standardwert verwendet, wenn Sie nicht der Befehlstext in [CCommand::Open](../../data/oledb/ccommand-open.md)\-Methode angeben.  
  
 Dieses Makro akzeptiert ANSI\-Zeichenfolgen, wenn Sie die Anwendung als ANSI erstellen, oder Unicode\-Zeichenfolgen, wenn Sie die Anwendung als Unicode erstellen.  Es wird empfohlen, dass Sie [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) anstelle `DEFINE_COMMAND`, da das frühere Unicode\-Zeichenfolgen akzeptiert, unabhängig vom ANSI\- oder Unicode\-Anwendungstyp verwenden.  
  
## Beispiel  
 Siehe [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)