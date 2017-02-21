---
title: "Compilerwarnung (Stufe 1) C4364 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4364"
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#using für Assembly 'Datei' wurde zuvor unter Ort\(Zeilennummer\) ohne as\_friend\-Attribut gefunden; as\_friend wurde nicht angewendet  
  
 Eine `#using`\-Direktive für eine Metadatendatei wurde wiederholt, der `as_friend`\-Qualifizierer wurde im ersten Vorkommen jedoch nicht verwendet. Der Compiler ignoriert `as_friend` im zweiten Vorkommen.  
  
 Weitere Informationen finden Sie unter [Friend\-Assemblys \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md).  
  
## Beispiel  
 Das folgende Beispiel erstellt eine Komponente.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4364 generiert.  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```