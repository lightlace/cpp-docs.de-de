---
title: "Compilerfehler C2223"
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
  - "C2223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2223"
ms.assetid: e4506f0f-0317-4a96-8a90-877a156d7939
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der linke Teil von "\-\>Bezeichner" muss auf eine Struktur\/Union zeigen  
  
 Der Operand links von `->` ist kein Zeiger auf eine Klasse, Struktur oder Union.  
  
 Dieser Fehler kann durch einen linksseitigen Operanden verursacht werden, bei dem es sich um eine nicht definierte Variable handelt \(daher Typ `int`\).