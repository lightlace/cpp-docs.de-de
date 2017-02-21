---
title: "Compilerfehler C3173 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3173"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3173"
ms.assetid: edf79e10-e8cf-4f76-8d33-ab9d05e974e9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3173
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versionskonflikt beim Zusammenführen von idl  
  
 Dieser Fehler tritt auf, wenn eine Objektdatei eingebetteten IDL\-Inhalt aufweist, der mit einer früheren Compilerversion erstellt wurde.  Der Compiler codiert eine Versionsnummer, um sicherzustellen, dass der Compiler, mit dem der in die OBJ\-Dateien eingebettete IDL\-Inhalt erstellt wurde, mit dem Compiler identisch ist, mit dem der eingebettete IDL\-Inhalt zusammengeführt wurde.  
  
 Aktualisieren Sie die Visual C\+\+\-Installation, damit alle Tools die zuletzt freigegebene Version aufweisen.