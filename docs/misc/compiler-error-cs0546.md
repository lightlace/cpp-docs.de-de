---
title: "Compiler Error CS0546"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0546"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0546"
ms.assetid: d259c86f-ee29-4e2d-b381-6ba7252af87e
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compiler Error CS0546
"Accessor": Überschreiben nicht möglich, weil "Eigenschaft" keinen überschreibbaren set\-Accessor hat.  
  
 Beim Versuch, eine der Accessormethoden für eine Eigenschaft zu überschreiben, ist ein Fehler aufgetreten, da der Accessor nicht überschrieben werden kann. Dieser Fehler kann in folgenden Fällen auftreten:  
  
-   Die Basisklasse ist nicht als [virtuell](../Topic/virtual%20\(C%23%20Reference\).md) deklariert.  
  
-   Die Basisklasseneigenschaft deklariert den [get](../Topic/get%20\(C%23%20Reference\).md)\- oder [set](../Topic/set%20\(C%23%20Reference\).md)\-Accessor nicht, den Sie überschreiben möchten.  
  
 Wenn Sie die Basisklasseneigenschaft nicht überschreiben möchten, können Sie vor der Eigenschaft in einer abgeleiteten Klasse das [new](../Topic/new%20\(C%23%20Reference\).md)\-Schlüsselwort verwenden.  
  
 Weitere Informationen finden Sie unter [Verwenden von Eigenschaften](../Topic/Using%20Properties%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgende Beispiel wird CS0546 generiert, da die Basisklasse keinen set\-Accessor für die Eigenschaft deklariert.  
  
```  
// CS0546.cs // compile with: /target:library public class a { public virtual int i { get { return 0; } } public virtual int i2 { get { return 0; } set {} } } public class b : a { public override int i { set {}   // CS0546 error no set } public override int i2 { set {}   // OK } }  
```  
  
## Siehe auch  
 [Eigenschaften](../Topic/Properties%20\(C%23%20Programming%20Guide\).md)