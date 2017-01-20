---
title: "Compilerfehler C2553"
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
  - "C2553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2553"
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Basisfunktion': Der Rückgabetyp der überschreibenden virtuellen Funktion unterscheidet sich von 'Überschreibungsfunktion'  
  
 Eine Funktion in einer abgeleiteten Klasse hat versucht, eine virtuelle Funktion in einer Basisklasse zu überschreiben, die abgeleitete Klassenfunktion hatte jedoch einen anderen Rückgabetyp als die Basisklassenfunktion.  Die Signatur einer Überschreibungsfunktion muss mit der Signatur der überschriebenen Funktion übereinstimmen.  
  
 Im folgenden Beispiel wird C2553 generiert:  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```