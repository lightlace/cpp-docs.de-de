---
title: "Compilerwarnung (Stufe 1) C4788 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4788"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4788"
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 1) C4788
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Der Bezeichner wurde auf 'Anzahl' Zeichen gekürzt.  
  
 Durch den Compiler wird die für einen Funktionsnamen zugelassene maximale Länge eingeschränkt.  Wenn vom Compiler funclets für EH\/SEH\-Code generiert werden, entsteht der funclet\-Name, indem dem Funktionsnamen Text \(z. B. "\_\_catch", "\_\_unwind" oder eine andere Zeichenfolge\) vorangestellt wird.  
  
 Wenn der erstellte funclet\-Name zu lang ist, wird dieser vom Compiler gekürzt, und es wird C4788 ausgegeben.  
  
 Um diese Warnung zu vermeiden, kürzen Sie den ursprünglichen Funktionsnamen.  Wenn es sich bei der Funktion um eine C\+\+\-Vorlagenfunktion oder \-Methode handelt, verwenden Sie für einen Teil des Namens eine Typdefinition.  Beispiel:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 Dies kann durch Folgendes ersetzt werden:  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Diese Warnung tritt nur im [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Compiler auf.