---
title: "Linkertoolfehler LNK1302 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1302"
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Linkertoolfehler LNK1302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie unterstützen nur das Verknüpfen des Safes .netmodules; Ein der Linkdatei .netmodule  
  
 . NETMODULE\-Datei \(mit **\/LN** kompiliert\) wurde den Linker in einem beim, MSIL\-Verknüpfung an.  Ein C\+\+\-Modul ist für die MSIL\-Verknüpfung gültig, wenn es mit **\/clr:safe** kompiliert wird.  
  
 Kompilieren Sie mit **\/clr:safe**, um die MSIL\-Verknüpfung zu ermöglichen, oder übergeben Sie die **\/clr**\- oder **\/clr:pure**\-OBJ\-Datei anstelle des Moduls an den Linker, um diesen Fehler zu beheben.  
  
 Weitere Informationen finden Sie unter  
  
-   [\/LN \(Erstellen eines MSIL\-Moduls\)](../../build/reference/ln-create-msil-module.md)  
  
-   [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)