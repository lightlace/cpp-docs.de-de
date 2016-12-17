---
title: "Compilerwarnung (Stufe 1) C4190"
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
  - "C4190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4190"
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner1' hat C\-Bindung angegeben, aber gibt UDT 'Bezeichner2' zurück, was mit C inkompatibel ist  
  
 Eine Funktion oder ein Zeiger auf eine Funktion verfügt über einen UDT \(benutzerdefinierter Typ vom Typ Klasse, Struktur, Enumeration, Union oder [\_\_value](../../misc/value.md)\) als Rückgabetyp und über `extern` "C"\-Bindung.  Dies ist unter folgenden Voraussetzungen zulässig:  
  
-   Alle Aufrufe dieser Funktion erfolgen von C\+\+ aus.  
  
-   Die Funktion wurde in C\+\+ definiert.  
  
## Beispiel  
  
```  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```