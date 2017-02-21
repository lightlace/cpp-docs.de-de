---
title: "Compilerfehler C3451 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3451"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3451"
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Compilerfehler C3451
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Attribut': Ein nicht verwaltetes Attribut kann nicht auf 'Typ' angewendet werden  
  
 Ein C\+\+\-Attribut kann nicht auf einen CLR\-Typ angewendet werden.  Weitere Informationen finden Sie unter [C\+\+ Attributes Reference](../../windows/cpp-attributes-reference.md).  
  
 Weitere Informationen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Dieser Fehler kann infolge einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 ausgegeben werden: Das Attribut [uuid](../../windows/uuid-cpp-attributes.md) ist nicht mehr für ein benutzerdefiniertes Attribut mit der CLR\-Programmierung zulässig.  Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.GuidAttribute>.  
  
## Beispiel  
 Im folgenden Beispiel wird C3451 generiert.  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```