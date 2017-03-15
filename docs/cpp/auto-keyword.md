---
title: "Auto-Schl&#252;sselwort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "auto"
  - "auto_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto-Schlüsselwort"
  - "Automatische Speicherklasse, auto-Schlüsselwort"
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Auto-Schl&#252;sselwort
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `auto`\-Schlüsselwort ist ein Deklarationsspezifizierer.  Der C\+\+\-Standard definiert jedoch eine ursprüngliche und eine überarbeitete Bedeutung für dieses Schlüsselwort.  Bis zu [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] deklariert das `auto`\-Schlüsselwort eine Variable in der *automatic*\-Speicherklasse, d. h. eine Variable, die über eine lokale Lebensdauer verfügt.  Ab [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] deklariert das`auto`\-Schlüsselwort eine Variable, deren Typ aus dem Initialisierungsausdruck in der entsprechenden Deklaration abgeleitet wird.  Die [\/Zc:auto&#91;\-&#93;](../build/reference/zc-auto-deduce-variable-type.md)\-Compileroption steuert die Bedeutung des `auto`\-Schlüsselworts.  
  
## Syntax  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## Hinweise  
 Die Definition des `auto`\-Schlüsselworts ändert sich in der Programmiersprache C\+\+, aber nicht in der Programmiersprache C.  
  
 In den folgenden Themen wird das `auto`\-Schlüsselwort und die entsprechende Compileroption beschrieben:  
  
-   [auto](../cpp/auto-cpp.md) beschreibt die neue Definition des `auto`\-Schlüsselworts.  
  
-   [\(NOTINBUILD\)auto Keyword \(Storage\-Class Specifier\)](assetId:///c7d0cecf-393d-4058-a6e6-b39e31d9edb0) beschreibt die ursprüngliche Definition des `auto`\-Schlüsselworts.  
  
-   [\/Zc:auto \(Variablentyp ableiten\)](../build/reference/zc-auto-deduce-variable-type.md) beschreibt die Compileroption, die dem Compiler mitteilt, welche Definition des `auto`\-Schlüsselworts verwendet werden soll.  
  
## Siehe auch  
 [\(NOTINBUILD\)Storage\-Class Specifiers](assetId:///10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)