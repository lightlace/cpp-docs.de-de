---
title: "Compilerfehler C3173"
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
  - "C3173"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3173"
ms.assetid: edf79e10-e8cf-4f76-8d33-ab9d05e974e9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3173
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versionskonflikt beim Zusammenführen von idl  
  
 Dieser Fehler tritt auf, wenn eine Objektdatei eingebetteten IDL\-Inhalt aufweist, der mit einer früheren Compilerversion erstellt wurde.  Der Compiler codiert eine Versionsnummer, um sicherzustellen, dass der Compiler, mit dem der in die OBJ\-Dateien eingebettete IDL\-Inhalt erstellt wurde, mit dem Compiler identisch ist, mit dem der eingebettete IDL\-Inhalt zusammengeführt wurde.  
  
 Aktualisieren Sie die Visual C\+\+\-Installation, damit alle Tools die zuletzt freigegebene Version aufweisen.