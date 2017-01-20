---
title: "Compilerfehler C2011"
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
  - "C2011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2011"
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": "Typ" Typneudefinition  
  
 Der Bezeichner wurde bereits als `type` definiert.  Überprüfen Sie, ob Neudefinitionen des Bezeichners vorliegen.  
  
 Beim Import tritt möglicherweise auch der Fehler C2011 auf, wenn Sie eine Headerdatei oder Typbibliothek mehrfach in dieselbe Datei importieren.  Verwenden Sie include\-Schutz oder eine `#pragma` [once](../../preprocessor/once.md)\-Direktive in der Headerdatei, um mehrfache Einbindungen von in einer Headerdatei definierten Typen zu verhindern.  
  
 Wenn Sie die ursprüngliche Deklaration eines neu definierten Typs benötigen, können Sie mit dem [\/P](../../build/reference/p-preprocess-to-a-file.md)\-Compilerflag die vorverarbeitete an den Compiler übergebene Ausgabe generieren.  Mit Textsuchtools können Sie nach Instanzen der neu definierten Bezeichner in der Ausgabedatei suchen.  
  
 Im folgenden Beispiel wird C2011 generiert und eine Möglichkeit gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```