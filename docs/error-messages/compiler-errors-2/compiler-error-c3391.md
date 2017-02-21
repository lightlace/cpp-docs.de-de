---
title: "Compilerfehler C3391 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3391"
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typargument': Ungültiges Typargument für den generischen Parameter 'Param' von 'generischer\_Typ' \(generisch\). Muss ein Werttyp sein, der keine NULL\-Werte zulässt.  
  
 Ein generischer Typ wurde fehlerhaft instanziiert.  Überprüfen Sie die Typdefinition.  Weitere Informationen finden Sie unter <xref:System.Nullable> und [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird mit C\# eine Komponente erstellt, die einen generischen Typ mit bestimmten Einschränkungen enthält, die nicht unterstützt werden, wenn generische Typen in [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)] geschrieben werden. Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
```  
// C3391.cs // compile with: /target:library // a C# program public class GR<N> where N : struct {}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3391 generiert:  
  
```  
// C3391_b.cpp // compile with: /clr #using <C3391.dll> using namespace System; value class VClass {}; int main() { GR< Nullable<VClass> >^ a = gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable GR<VClass>^ aa = gcnew GR<VClass>();   // OK }  
```