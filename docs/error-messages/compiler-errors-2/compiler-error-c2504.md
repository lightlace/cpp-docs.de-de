---
title: "Compilerfehler C2504 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2504"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2504"
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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