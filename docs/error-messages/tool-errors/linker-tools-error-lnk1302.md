---
title: "Linkertoolfehler LNK1302"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1302"
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie unterstützen nur das Verknüpfen des Safes .netmodules; Ein der Linkdatei .netmodule  
  
 . NETMODULE\-Datei \(mit **\/LN** kompiliert\) wurde den Linker in einem beim, MSIL\-Verknüpfung an.  Ein C\+\+\-Modul ist für die MSIL\-Verknüpfung gültig, wenn es mit **\/clr:safe** kompiliert wird.  
  
 Kompilieren Sie mit **\/clr:safe**, um die MSIL\-Verknüpfung zu ermöglichen, oder übergeben Sie die **\/clr**\- oder **\/clr:pure**\-OBJ\-Datei anstelle des Moduls an den Linker, um diesen Fehler zu beheben.  
  
 Weitere Informationen finden Sie unter  
  
-   [\/LN \(Erstellen eines MSIL\-Moduls\)](../../build/reference/ln-create-msil-module.md)  
  
-   [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)