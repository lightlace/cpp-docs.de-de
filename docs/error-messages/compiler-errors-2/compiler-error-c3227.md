---
title: "Compilerfehler C3227"
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
  - "C3227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3227"
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Parameter': 'Schlüsselwort' kann nicht für die Zuweisung eines generischen Typs verwendet werden  
  
 Zum Instanziieren eines Typs ist ein entsprechender Konstruktor erforderlich.  Der Compiler garantiert jedoch nicht, dass ein geeigneter Konstruktor verfügbar ist.  
  
 Zur Behebung dieses Fehlers können Sie anstelle von Generika Vorlagen verwenden, oder Sie können mit einer der verfügbaren Methoden eine Instanz des Typs erstellen.  
  
## Beispiel  
 Im folgenden Beispiel wird C3227 generiert.  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```