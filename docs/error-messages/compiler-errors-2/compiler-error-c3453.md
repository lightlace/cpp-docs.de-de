---
title: "Compilerfehler C3453 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3453"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3453"
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3453
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut': Das Attribut wurde nicht angewendet, da der Qualifizierer 'assembly' nicht übereinstimmte.  
  
 Attribute auf Assembly\- oder Modulebene können nur als eigenständige Anweisungen angegeben werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3453 generiert:  
  
```  
// C3453.cpp // compile with: /clr /c [assembly:System::CLSCompliant(true)]   // C3453 // try the following line instead // [assembly:System::CLSCompliant(true)]; ref class X {};  
```