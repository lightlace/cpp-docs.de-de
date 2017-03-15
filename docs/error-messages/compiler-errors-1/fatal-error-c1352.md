---
title: "Schwerwiegender Fehler C1352 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1352"
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige oder beschädigte MSIL in "Funkion"\-Funktion aus Modul "Datei".  
  
 Eine NETMODULE\-Datei wurde an den Compiler übergeben, aber der Compiler hat eine Beschädigung in der Datei erkannt.  Bitten Sie die Person, die die NETMODULE\-Datei erstellt hat, diese zu überprüfen.  
  
 Der Compiler überprüft NETMODULE\-Dateien nicht auf alle Arten von Beschädigung.  Er prüft jedoch, ob alle Steuerelementpfade in einer Funktion eine return\-Anweisung enthalten.  
  
 Weitere Informationen finden Sie unter [NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).