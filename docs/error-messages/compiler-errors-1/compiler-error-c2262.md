---
title: "Compilerfehler C2262"
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
  - "C2262"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2262"
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2262
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"attribute\_specifiers": Für InternalsVisibleTo\-Deklarationen kann keine Version, Kultur oder Prozessorarchitektur angegeben sein  
  
 Das <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>\-Attribut wurde nicht ordnungsgemäß angegeben.  
  
## Beispiel  
 Im folgenden Beispiel wird C2262 generiert.  
  
```  
// C2262.cpp // compile with: /clr /c using namespace System::Runtime::CompilerServices; [assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262 [assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```