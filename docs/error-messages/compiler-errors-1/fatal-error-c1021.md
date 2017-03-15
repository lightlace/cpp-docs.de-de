---
title: "Schwerwiegender Fehler C1021 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1021"
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Schwerwiegender Fehler C1021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Präprozessorbefehl 'string'  
  
 `string` ist keine gültige [Präprozessordirektive](../../preprocessor/preprocessor-directives.md). Um den Fehler zu beheben, verwenden Sie einen gültigen Präprozessornamen für `string`.  
  
 Im folgenden Beispiel wird C1021 generiert:  
  
```  
// C1021.cpp #BadPreProcName    // C1021 delete line  
```