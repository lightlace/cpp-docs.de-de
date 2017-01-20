---
title: "Compilerfehler C3290"
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
  - "C3290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3290"
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Eine trivial\-Eigenschaft darf keinen Referenztyp aufweisen.  
  
 Eine Eigenschaft wurde falsch deklariert. Wenn Sie eine triviale Eigenschaft deklarieren, erstellt der Compiler eine Variable, die von der Eigenschaft aktualisiert wird, und es ist nicht möglich, eine Nachverfolgungsverweisvariable in einer Klasse zu verwenden.  
  
 Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) und [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3290 generiert.  
  
```  
// C3290.cpp // compile with: /clr /c ref struct R {}; ref struct X { R^ mr; property R % y;   // C3290 property R ^ x;   // OK // OK property R% prop { R% get() { return *mr; } void set(R%) {} } }; int main() { X x; R% xp = x.prop; }  
```