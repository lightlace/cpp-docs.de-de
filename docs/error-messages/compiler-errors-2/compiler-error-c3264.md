---
title: "Compilerfehler C3264"
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
  - "C3264"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3264"
ms.assetid: 94ece687-2364-4f7a-8ebb-7afd3ae9d63d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3264
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Ein Klassenkonstruktor kann keinen Rückgabetyp haben  
  
 Klassenkonstruktoren können keine Rückgabetypen aufweisen.  
  
 Im folgenden Beispiel wird C3264 generiert:  
  
```  
// C3264_2.cpp // compile with: /clr ref class X { public: static int X()   { // C3264 } /* use the code below to resolve the error static X() { } */ }; int main() { }  
```  
  
 Im folgenden Beispiel wird C3264 generiert:  
  
```  
// C3264.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc class X { public: static int X()   { // C3264 } /* use the code below to resolve the error static X() { } */ }; int main() { }  
```