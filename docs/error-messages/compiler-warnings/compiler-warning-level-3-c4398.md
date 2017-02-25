---
title: "Compilerwarnung (Stufe 3) C4398 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4398"
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 3) C4398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Prozessspezifische globale Objekte funktionieren bei mehreren Anwendungsdomänen möglicherweise nicht korrekt; verwenden Sie ggf. \_\_declspec\(anwendungsdomänenspezifisch\)  
  
 Eine virtuelle Funktion mit der [\_\_clrcall](../../cpp/clrcall.md)\-Aufrufkonvention in einem systemeigenen Typ bewirkt die Erstellung einer anwendungsdomänenspezifischen vtable.  Solch eine Variable wird möglicherweise nicht ordnungsgemäß korrigiert, wenn sie in mehreren Anwendungsdomänen verwendet wird.  
  
 Sie können diese Warnung vermeiden, wenn Sie mit **\/clr:pure** kompilieren. Dadurch werden globale Variablen standardmäßig anwendungsdomänenspezifisch. Wahlweise können Sie die Variable mit `__declspec(appdomain)` kennzeichnen.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [Anwendungsdomänen und Visual C\+\+](../../dotnet/application-domains-and-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4398 generiert.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```