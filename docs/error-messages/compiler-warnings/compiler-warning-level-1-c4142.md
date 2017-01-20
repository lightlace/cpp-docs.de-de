---
title: "Compilerwarnung (Stufe 1) C4142"
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
  - "C4142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4142"
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neudefinition eines Typs ohne Auswirkungen  
  
 Ein Typ wurde neu definiert, was jedoch keine Auswirkungen auf den erzeugten Code hat.  
  
 Dieser Fehler kann eine der folgenden Ursachen haben:  
  
-   Eine Memberfunktion einer abgeleiteten Klasse verfügt über einen anderen Rückgabetyp als die entsprechende Memberfunktion der Basisklasse.  
  
-   Ein mit dem `typedef`\-Befehl definierter Typ wird mit einer anderen Syntax neu definiert.  
  
 Im folgenden Beispiel wird C4142 generiert:  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```