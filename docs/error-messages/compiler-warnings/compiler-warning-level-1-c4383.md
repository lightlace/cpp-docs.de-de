---
title: "Compilerwarnung (Stufe 1) C4383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4383"
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Instanzendereferenzierungsoperator': Die Bedeutung der Dereferenzierung eines Handles kann sich ändern, wenn ein benutzerdefinierter Operator 'Operator' vorhanden ist. Schreiben Sie den Operator als statische Funktion, damit der Operand explizit ist.  
  
 Wenn Sie eine benutzerdefinierte Instanzenüberschreibung des Dereferenzierungsoperators in einem verwalteten Typ hinzufügen, ist der Dereferenzierungsoperator des Typs unter Umständen nicht mehr in der Lage, das Objekt für den Handle zurückzugeben.  Es wird empfohlen, einen statischen benutzerdefinierten Dereferenzierungsoperator zu schreiben.  
  
 Weitere Informationen finden Sie unter [Handle für Objekt \(^\)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) und [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
 Des Weiteren steht ein Instanzenoperator anderen Sprachcompilern über referenzierte Metadaten nicht zur Verfügung.  Weitere Informationen finden Sie unter [Benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4383 generiert.  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```