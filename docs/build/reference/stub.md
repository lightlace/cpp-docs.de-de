---
title: "STUB"
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
  - "STUB"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STUB-Anweisung in DEF-Dateien"
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# STUB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn die Anweisung in einer Moduldefinitionsdatei zum Erstellen eines virtuellen Gerätetreibers \(VxD\) verwendet wird, bietet STUB die Möglichkeit, den Namen einer Datei mit einer \(in WINNT.H definierten\) IMAGE\_DOS\_HEADER\-Struktur anzugeben, die anstelle des Standardheaders im virtuellen Gerätetreiber \(VxD\) verwendet werden soll.  
  
```  
STUB:filename  
```  
  
## Hinweise  
 Alternativ können Sie *filename* auch mit der [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)\-Linkeroption festlegen.  
  
 STUB ist in einer Moduldefinitionsdatei nur beim Erstellen eines VxD gültig.  
  
## Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)