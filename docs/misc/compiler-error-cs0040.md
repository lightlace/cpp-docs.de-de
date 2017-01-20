---
title: "Compilerfehler CS0040"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0040"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0040"
ms.assetid: 6a600166-0335-4b6d-b050-6821b4624c96
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0040
Unerwarteter Fehler beim Erstellen der Debuginformationsdatei – "Ursache"  
  
 Dieser Fehler kann bei Verwendung der Compileroption [\/debug](../Topic/-debug%20\(C%23%20Compiler%20Options\).md) auftreten und gibt an, dass der Compiler nicht in die PDB\-Datei schreiben konnte. Mögliche Lösungen für dieses Problem: Installieren Sie Visual Studio neu, und stellen Sie sicher, dass der Compiler Schreibzugriff auf eine Datei oder ein Verzeichnis hat, oder kompilieren Sie ohne die Option "\/debug".