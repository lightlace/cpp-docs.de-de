---
title: "Compilerfehler C3320"
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
  - "C3320"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3320"
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3320
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Typ kann nicht den gleichen Namen besitzen wie die name\-Moduleigenschaft.  
  
 Ein exportierter benutzerdefinierter Typ \(UDT\), bei dem es sich um eine Struktur, Klasse, Enumeration, Union oder [\_\_value](../../misc/value.md) handeln kann, darf nicht denselben Namen wie der Parameter verwenden, der an die name\-Eigenschaft des [module](../../windows/module-cpp.md)\-Attributs übergeben wird.  
  
 Im folgenden Beispiel wird C3320 generiert:  
  
```  
// C3320.cpp #include "unknwn.h" [module(name="xx")]; [export] struct xx {   // C3320 // Try the following line instead // [export] struct yy { int i; };  
```