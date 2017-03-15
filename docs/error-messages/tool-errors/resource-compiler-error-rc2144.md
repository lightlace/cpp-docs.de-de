---
title: "Ressourcencompiler: Fehler RC2144 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2144"
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ressourcencompiler: Fehler RC2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Primäre Sprach\-ID ist keine Zahl  
  
 Primäre Sprach\-ID muss eine hexadezimale Sprachen\-ID sein.  Unter [Sprach\- und Länder\-\/Regionen\-Strings](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) in der *Laufzeit\-Bibliothek\-Referenz* finden Sie eine Liste der gültigen Sprach\-IDs.  
  
 Dieser Fehler kann auch auftreten, wenn Sie Ressourcen hinzugefügt und aus der.RC\-Datei mithilfe des Tools gelöscht haben.  Um dieses Problem zu beheben, öffnen Sie die.RC\-Datei in einem Texteditor und bereinigen Sie manuell alle nicht verwendeten Ressourcen.