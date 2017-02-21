---
title: "Compilerfehler C3153 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3153"
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3153
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schnittstelle': Sie können keine Instanz einer Schnittstelle erzeugen  
  
 Eine Schnittstelle kann nicht instanziiert werden.  Um die Member einer Schnittstelle zu verwenden, leiten Sie eine Klasse von der Schnittstelle ab und implementieren dann die Schnittstellenmember, bevor Sie die Member einsetzen.  
  
 Im folgenden Beispiel wird C3153 generiert:  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  
  
 Im folgenden Beispiel wird C3153 generiert:  
  
```  
// C3153b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__interface A {  
};  
  
int main() {  
   A *a = new A;   // C3153  
}  
```