---
title: "Compilerfehler C2857"
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
  - "C2857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2857"
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die mit der Befehlszeilenoption \/YcDateiname festgelegte '\#include'\-Anweisung konnte in der Quelldatei nicht gefunden werden  
  
 In der [\/Yc](../../build/reference/yc-create-precompiled-header-file.md)\-Option wird der Name einer Includedatei angegeben, die jedoch nicht in der kompilierten Quelldatei enthalten ist.  
  
 Dieser Fehler kann durch eine `#include`\-Anweisung in einem Block für die bedingte Kompilierung verursacht werden, wenn dieser nicht kompiliert ist.