---
title: "Compilerfehler C2768"
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
  - "C2768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2768"
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Unzulässige Verwendung von expliziten Vorlagenargumenten  
  
 Der Compiler konnte nicht feststellen, ob eine Funktionsdefinition eine explizite Spezialisierung einer Funktionsvorlage sein sollte oder ob sie für eine neue Funktion bestimmt war.  
  
 Dieser Fehler resultiert aus den Verbesserungen der Compilerkonformität in Visual Studio .NET 2003.  
  
 Im folgenden Beispiel wird C2768 generiert:  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```