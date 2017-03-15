---
title: "Linkertoolfehler LNK1000 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1000"
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Linkertoolfehler LNK1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unbekannter Fehler. In der Dokumentation finden Sie weitere Informationen zum Software Service.  
  
 Notieren Sie die Begleitumstände des Fehlers, versuchen Sie, das Problem zu isolieren und einen reproduzierbaren Testfall zu erstellen, und wenden Sie sich dann an `Microsoft Product Support Services`.  Informationen darüber, wie Sie zu diesen Fehlern finden, Sie untersucht und feststellt [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Dieser Fehler tritt möglicherweise auf, wenn Sie Standardheaderdateien \(z. B., dos.h\) und eigene Dateien kombinieren.  Fügen Sie die Standardheader zuerst mit `#include` hinzu, und fügen Sie dann Ihren eigenen Headerdateien ein.