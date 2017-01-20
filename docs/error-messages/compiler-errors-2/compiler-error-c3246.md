---
title: "Compilerfehler C3246"
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
  - "C3246"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3246"
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3246
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'klasse': Von 'typ' kann nicht geerbt werden, da er als 'sealed' \(versiegelt\) deklariert wurde  
  
 Eine Klasse, die als [versiegelt](../../misc/sealed.md) gekennzeichnet ist, kann nicht die Basisklasse für andere Klassen bilden.  
  
 Im folgenden Beispiel wird C3246 generiert:  
  
```  
// C3246_2.cpp // compile with: /clr /LD ref class X sealed {}; ref class Y : public X {}; // C3246  
```  
  
 Im folgenden Beispiel wird C3246 generiert:  
  
```  
// C3246.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> __sealed __gc class X {}; __gc class Y : public X {}; // C3246  
```