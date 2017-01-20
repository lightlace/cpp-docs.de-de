---
title: "Compilerfehler C2504"
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
  - "C2504"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2504"
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2504
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Basisklasse undefiniert  
  
 Die Basisklasse wurde zwar deklariert, aber nie definiert.  Mögliche Ursachen:  
  
1.  Fehlende Includedatei.  
  
2.  Die externe Basisklasse wurde nicht mit [extern](../../cpp/using-extern-to-specify-linkage.md) deklariert.  
  
 Im folgenden Beispiel wird C2504 generiert:  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 \/\/ OK  
  
```  
class C{};  
class D : public C {};  
```