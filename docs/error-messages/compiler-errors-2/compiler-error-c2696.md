---
title: "Compilerfehler C2696"
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
  - "C2696"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2696"
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2696
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es kann kein temporäres Objekt eines verwalteten Typs 'Typ' erstellt werden  
  
 Wenn in einem nicht verwalteten Programm Verweise auf `const` enthalten sind, ruft der Compiler den Konstruktor auf und erstellt ein temporäres Objekt auf dem Stapel.  Eine verwaltete Klasse kann auf dem Stapel jedoch grundsätzlich nicht erstellt werden.  
  
 C2696 ist nur über **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C2696 generiert:  
  
```  
// C2696b.cpp  
// compile with: /clr:oldSyntax  
  
__gc class G {  
public:  
   G( int i ) {}  
};  
  
void func( const G& g );  
  
int main() {  
   func( 1 );   // C2696  
   G *myG = new G( 1 );   // OK  
   func( *myG );  
}  
```