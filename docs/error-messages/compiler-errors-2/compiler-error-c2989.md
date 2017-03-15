---
title: "Compilerfehler C2989 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2989"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2989"
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2989
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Klassentyp wurde bereits als Nicht\-Klassentyp deklariert  
  
 Die generische oder Vorlagenklasse definiert eine nicht auf Vorlagen basierende oder nicht generische Klasse neu.  Prüfen Sie die Headerdateien auf Konflikte.  
  
 Wenn Sie Teilspezialisierungen einer Klassenvorlage verwenden, informieren Sie sich im Knowledge Base\-Artikel Q240866 \(nur auf Englisch verfügbar\).  
  
 Im folgenden Beispiel wird C2989 generiert:  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 C2989 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```