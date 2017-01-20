---
title: "Compilerfehler C2530"
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
  - "C2530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2530"
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Verweise müssen initialisiert werden  
  
 Nach der Deklaration muss ein Verweis initialisiert werden, es sei denn, dies ist bereits geschehen:  
  
-   Mit dem Schlüsselwort [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
-   Als Member einer Klasse, Struktur oder Union \(und er wird im Konstruktor initialisiert\).  
  
-   Als Parameter in einer Funktionsdeklaration oder \-definition.  
  
-   Als Rückgabetyp einer Funktion.  
  
 Im folgenden Beispiel wird C2530 generiert:  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```