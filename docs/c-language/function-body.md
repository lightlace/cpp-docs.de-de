---
title: "Funktionsrumpf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionsrumpf"
  - "Funktionsdefinitionen, Funktionsrumpf"
  - "Funktionen [C], Syntax"
  - "Variablen, Funktionssyntax"
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Funktionsrumpf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein "Funktionsrumpf" entspricht einer Verbundanweisung mit den Anweisungen, die die Aufgabe der Funktion angeben.  
  
## Syntax  
 *function\-definition*:  
 *declaration\-specifiers*  opt *attribute\-seq* opt *declarator declaration\-list* opt *compound\-statement*  
  
 \/\* *attribute\-seq* ist Microsoft\-spezifisch \*\/  
  
 *compound\-statement*: \/\* Der Funktionsrumpf\*\/  
 **{**  *declaration\-list*  opt *statement\-list* opt **}**  
  
 Variablen, die in einem Funktionsrumpf "lokal" deklariert werden, weisen die **auto**\-Speicherklasse auf, sofern nicht anders angegeben ist.  Wenn die Funktion aufgerufen wird, wird Speicherplatz für die lokalen Variablen erstellt, und lokale Initialisierungen werden ausgeführt.  Die Ausführungssteuerung wird an die erste Anweisung in *compound\-statement* übergeben und fährt fort, bis eine `return`\-Anweisung ausgeführt wurde oder das Ende des Funktionsrumpfs erreicht ist.  Anschließend wird die Steuerung wieder an den Punkt zurückgegeben, an dem die Funktion aufgerufen wurde.  
  
 Eine `return`\-Anweisung, die einen Ausdruck enthält, muss ausgeführt werden, wenn die Funktion einen Wert zurückgeben soll.  Der Rückgabewert einer Funktion ist nicht definiert, wenn keine `return`\-Anweisung ausgeführt wird oder wenn die `return`\-Anweisung keinen Ausdruck enthält.  
  
## Siehe auch  
 [C\-Funktionsdefinitionen](../c-language/c-function-definitions.md)