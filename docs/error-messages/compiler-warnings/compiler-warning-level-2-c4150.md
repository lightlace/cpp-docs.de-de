---
title: "Compilerwarnung (Stufe 2) C4150"
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
  - "C4150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4150"
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Löschen eines Zeigers auf den nicht definierten Typ 'Typ'. Destruktor wurde nicht aufgerufen  
  
 Der Operator **delete** wurde zum Löschen eines Typs aufgerufen, der zwar deklariert, aber nicht definiert wurde, sodass der Compiler keinen Destruktor finden konnte.  
  
 Im folgenden Beispiel wird C4150 generiert:  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```