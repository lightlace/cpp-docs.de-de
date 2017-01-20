---
title: "Compilerfehler C2722"
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
  - "C2722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2722"
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::Operator': Nach Operatorbefehl unzulässig; verwenden Sie 'Operator Operator'  
  
 Eine `operator`\-Anweisung definiert `::new` oder `::delete` neu.  Da die Operatoren `new` und `delete` global sind, hat der Bereichsauflösungsoperator \(`::`\) keine Bedeutung.  Entfernen Sie den Operator `::`.