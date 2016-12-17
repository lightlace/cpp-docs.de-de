---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1052"
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
  - "RC1052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1052"
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Schwerwiegender Fehler RC1052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compiler\-Grenzen: \#if\- oder \#ifdef\-Blöcke sind zu tief geschachtelt.  
  
 Die maximal zulässige Schachtelungstiefe für `#if`\- und `#ifdef`\-Direktiven wird vom Programm überschritten.  
  
 Dieser Fehler kann durch Includedateien, die diese Präprozessordirektiven verwenden, verursacht werden.  
  
 Um dieses Problem zu beheben, verringern Sie die Anzahl der geschachtelten `#if`\- und `#ifdef`\-Direktiven in der Ressourcendatei.  Wenn das Problem durch Header\-Dateien verursacht wird, die in der Ressourcendatei enthalten sind, verringern Sie die Anzahl der geschachtelten `#if` und `#ifdef`\-Direktiven in den Headerdateien.  Wenn dies nicht möglich ist, sollten Sie eine neue Headerdatei in Ihrer Ressourcendatei mit dem Präprozessor auf vorhandenen eingeschlossenen Headerdateien erstellen und einschließen.  Weitere Informationen finden Sie unter Compilerfehler [\/P \(Vorverarbeitung in eine Datei\)](../../build/reference/p-preprocess-to-a-file.md).