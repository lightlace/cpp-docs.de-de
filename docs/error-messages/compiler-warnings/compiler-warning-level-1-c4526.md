---
title: "Compilerwarnung (Stufe 1) C4526 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4526"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4526"
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4526
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Statische Memberfunktion kann die virtuelle Funktion 'virtuelle Funktion' nicht überschreiben.  Das Überschreiben wird ignoriert und die virtuelle Funktion ausgeblendet.  
  
 Die statische Memberfunktion erfüllt die Kriterien zum Überschreiben der virtuellen Funktion. Dadurch ist die Memberfunktion sowohl **virtual** als auch **static**.  
  
 Im folgenden Code wird C4526 generiert:  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Die folgenden Korrekturmaßnahmen sind möglich:  
  
-   Wenn die virtuelle Funktion der Basisklasse durch die Funktion überschrieben werden sollte, entfernen Sie den **static**\-Spezifizierer.  
  
-   Wenn die Funktion eine **static**\-Memberfunktion sein sollte, benennen Sie sie um, sodass kein Konflikt mit der virtuellen Funktion der Basisklasse entsteht.