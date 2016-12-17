---
title: "Compilerfehler C2261"
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
  - "C2261"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2261"
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2261
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeichenfolge': Der Assemblyverweis ist ungültig und kann nicht aufgelöst werden  
  
 Ein Wert war nicht gültig.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> wird verwendet, um eine Friend\-Assembly anzugeben.  Wenn beispielsweise b.dll von a.dll als Friend\-Assembly angegeben werden soll, würde \(in a.dll\) Folgendes angegeben werden: InternalsVisibleTo\("b"\).  Die Laufzeit lässt nun zu, dass b.dll auf alle Inhalte von a.dll Zugriff hat \(außer auf private Typen\).  
  
 Weitere Informationen über die richtige Syntax beim Angeben von Friend\-Assemblys finden Sie unter [Friend\-Assemblys \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2261 generiert.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```