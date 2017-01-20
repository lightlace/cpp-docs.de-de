---
title: "Compilerfehler C3628"
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
  - "C3628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3628"
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'base class': Verwaltete oder WinRT\-Klassen unterstützen nur die öffentliche Vererbung  
  
 Es wurde versucht, eine verwaltete oder WinRT\-Klasse als eine [private](../../cpp/private-cpp.md) oder [geschützte](../../cpp/protected-cpp.md) Basisklasse zu verwenden.  Eine verwaltete oder WinRT\-Klasse kann nur als eine Basisklasse mit [öffentlichem](../../cpp/public-cpp.md) Zugriff verwendet werden.  
  
 Im folgenden Beispiel wird C3628 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
  
 Im folgenden Beispiel wird C3628 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3628b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class B {  
};  
  
__gc class D : B {   // C3628, private is the default access level  
  
// The following line resolves the error.  
// __gc class D : public B {  
};  
  
int main() {  
}  
```