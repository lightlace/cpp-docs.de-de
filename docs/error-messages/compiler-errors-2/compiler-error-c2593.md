---
title: "Compilerfehler C2593"
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
  - "C2593"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2593"
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2593
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator Bezeichner' ist mehrdeutig  
  
 Für einen überladenen Operator wurden mehrere mögliche Operatoren definiert.  
  
 Dieser Fehler wird möglicherweise behoben, wenn Sie auf einen oder mehrere Parameter eine explizite Umwandlung anwenden.  
  
 Im folgenden Beispiel wird C2593 generiert:  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 Dieser Fehler kann verursacht werden, wenn mit einem `CArchive`\-Objekt eine Gleitkommavariable serialisiert wird.  Der Compiler identifiziert den Operator `<<` als mehrdeutig.  Die einzigen primitiven C\+\+\-Typen, die `CArchive` serialisieren kann, sind die Typen fester Größe `BYTE`, `WORD`, `DWORD` und `LONG`.  Alle ganzzahligen Typen müssen in einen dieser Typen für die Serialisierung umgewandelt werden.  Gleitkommatypen müssen mithilfe der `CArchive::Write()`\-Memberfunktion archiviert werden.  
  
 Das folgende Beispiel verdeutlicht die Archivierung einer Gleitkommavariablen \(`f`\) in einem Archiv `ar`:  
  
```  
ar.Write(&f, sizeof( float ));  
```