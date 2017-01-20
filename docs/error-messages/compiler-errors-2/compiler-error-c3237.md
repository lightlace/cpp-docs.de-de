---
title: "Compilerfehler C3237"
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
  - "C3237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3237"
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Generische\_Klasse": Eine generische Klasse kann kein benutzerdefiniertes Attribut sein.  
  
 Generische Klassen können keine benutzerdefinierten Attribute darstellen.  
  
## Beispiel  
 Im folgenden Beispiel wird C3237 generiert.  
  
```  
// C3237.cpp // compile with: /clr /c // C3237 expected using namespace System; generic <class T> // Delete the following line to resolve. [attribute(AttributeTargets::All, AllowMultiple=true)] public ref class GR {};  
```