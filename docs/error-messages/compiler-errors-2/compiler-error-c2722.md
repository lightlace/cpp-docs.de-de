---
title: "Compilerfehler C2722 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2722"
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::Operator': Nach Operatorbefehl unzulässig; verwenden Sie 'Operator Operator'  
  
 Eine `operator`\-Anweisung definiert `::new` oder `::delete` neu.  Da die Operatoren `new` und `delete` global sind, hat der Bereichsauflösungsoperator \(`::`\) keine Bedeutung.  Entfernen Sie den Operator `::`.