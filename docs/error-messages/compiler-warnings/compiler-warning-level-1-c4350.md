---
title: "Compilerwarnung (Stufe 1) C4350"
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
  - "C4350"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4350"
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4350
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verhaltensänderung: 'Member1' wird anstelle von 'Member2' aufgerufen  
  
 Ein R\-Wert darf nicht an einen nicht konstanten Verweis gebunden werden.  In früheren Versionen von Visual C\+\+ besteht die Möglichkeit, einen R\-Wert an einen nicht konstanten Verweis in einer direkten Initialisierung zu binden.  Durch diesen Code wird jetzt eine Warnung ausgegeben.  
  
 Um Rückwärtskompatibilität zu gewährleisten, können R\-Werte weiterhin an nicht konstante Verweise gebunden werden, nach Möglichkeit werden jedoch Standardkonvertierungen bevorzugt.  
  
 Diese Warnung stellt einer Änderung des Verhaltens gegenüber dem Visual C\+\+ .NET 2002\-Compiler dar.  Wenn diese Warnung aktiviert ist, wird sie unter Umständen auch für ordnungsgemäßen Code ausgegeben.  Die Warnung kann beispielsweise bei Verwendung der **std::auto\_ptr**\-Klassenvorlage auftreten.  
  
 Wenn diese Warnung ausgegeben wird, überprüfen Sie, ob für die Ausführung des Codes das Binden von R\-Werten an nicht konstante Verweise erforderlich ist.  Wenn Sie einen konstanten Verweis verwenden oder eine zusätzliche Überladung für konstante Verweise zur Verfügung stellen, kann dadurch das Problem gelöst werden.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4350 generiert:  
  
```  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```