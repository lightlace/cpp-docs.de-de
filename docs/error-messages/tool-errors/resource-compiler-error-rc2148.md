---
title: "Ressourcencompiler: Fehler RC2148 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2148"
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Fehler RC2148
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

TEILSPRACHEN\-ID zu groß  
  
 Der TEILSPRACHEN\-ID\-Wert lag außerhalb des gültigen Bereichs.  
  
 Die **LANGUAGE**\-Anweisung muss folgende Syntax aufweisen:  
  
 **LANGUAGE** *primary\_language\_ID*,*secondary\_language\_ID*  
  
 Gültige TEILSPRACHEN\-IDs werden in der Datei WINNT.h als SUBLANG\_\-Konstanten definiert.