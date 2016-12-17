---
title: "Ressourcencompiler: Warnung RC4093"
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
  - "RC4093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4093"
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Warnung RC4093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht mit Escapezeichen versehener Zeilenvorschub in Zeichenkonstante innerhalb des inaktiven Codes  
  
 Der konstante Ausdruck einer der Präprozessordirektiven `#if`, `#elif`, **\#ifdef** oder **\#ifndef** wurde zu 0 \(null\) ausgewertet, wodurch der nachfolgende Code unwirksam gemacht wurde.  Innerhalb des inaktiven Codes ist eine Zeilenendemarke in einem Satz von einfachen oder doppelten Anführungszeichen aufgetreten.  
  
 Jeglicher Text bis zum nächsten doppelten Anführungszeichen wurde als Teil einer Zeichenkonstanten interpretiert.