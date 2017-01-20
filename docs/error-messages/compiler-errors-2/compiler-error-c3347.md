---
title: "Compilerfehler C3347"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3347"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3347"
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3347
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Arg': Das erforderliche Argument ist nicht im Attribut 'idl\_modules' festgelegt.  
  
 Ein erforderliches Argument wurde nicht an das [idl\_module](../../windows/idl-module.md)\-Attribut übergeben.  
  
 Im folgenden Beispiel wird C3347 generiert:  
  
```  
// C3347.cpp // compile with: /c [module(name="xx")]; [idl_module(dllname="x")];    // C3347 // try the following line instead // [idl_module(name="test", dllname="x")];  
```