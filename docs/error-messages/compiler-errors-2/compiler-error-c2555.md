---
title: "Compilerfehler C2555 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2555"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2555"
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2555
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

' class1::function1': Der überschreibende virtuelle Funktionsrückgabetyp unterscheidet sich und ist keine 'covariant' von 'class2::function2'  
  
 Eine virtuelle Funktion und eine abgeleitete überschreibende Funktion verwenden dieselben Parameterlisten, aber unterschiedliche Rückgabetypen.  Eine überschreibende Funktion in einer abgeleiteten Klasse darf sich nicht nur hinsichtlich ihres Rückgabetyps von einer virtuellen Funktion in einer Basisklasse unterscheiden.  
  
 Um diesen Fehler zu beheben, führen Sie eine Typumwandlung für den Rückgabewert durch, nachdem die virtuelle Funktion aufgerufen wurde.  
  
 Dieser Fehler wird möglicherweise auch angezeigt, wenn Sie mit \/clr kompilieren.   Die Visual C\+\+\-Deklaration ist beispielsweise äquivalent zur folgenden C\#\-Deklaration:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Weitere Informationen zu C2555 finden Sie im Knowledge Base\-Artikel Q240862 \(nur auf Englisch verfügbar\).  
  
 Im folgenden Beispiel wird C2555 generiert:  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```