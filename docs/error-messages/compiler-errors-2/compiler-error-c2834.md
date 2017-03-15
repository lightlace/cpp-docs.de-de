---
title: "Compilerfehler C2834 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2834"
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Operator 'Operator' muss als global angegeben werden  
  
 Die Operatoren `new` and `delete` sind an die Klasse gebunden, in der sie enthalten sind.  Die Bereichsauflösung kann nicht verwendet werden, um eine Version von `new` oder `delete` aus einer anderen Klasse auszuwählen.  Um mehrere Formen des Operators `new` oder `delete` zu implementieren, erstellen Sie eine Operatorversion mit zusätzlichen formalen Parametern.