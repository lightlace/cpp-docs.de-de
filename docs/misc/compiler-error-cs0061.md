---
title: "Compilerfehler CS0061"
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
  - "CS0061"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0061"
ms.assetid: 8dfc57a9-653d-4902-a88c-92032ba64024
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0061
Inkonsistenter Zugriff: Auf die Basisschnittstelle 'interface 1' kann weniger zugegriffen werden als auf die Schnittstelle 'interface 2' .  
  
 Ein [public](../Topic/public%20\(C%23%20Reference\).md)\-Konstrukt muss ein Objekt zurückgeben, auf das öffentlich zugegriffen werden kann.  
  
 Der Schnittstellenzugriff kann in einer abgeleiteten Schnittstelle nicht eingeschränkt werden. Weitere Informationen finden Sie unter [Schnittstellen](../Topic/Interfaces%20\(C%23%20Programming%20Guide\).md) und [Zugriffsmodifizierer](../Topic/Access%20Modifiers%20\(C%23%20Programming%20Guide\).md).  
  
 Das folgende Beispiel generiert CS0061:  
  
```  
// CS0061.cs // compile with: /target:library internal interface A {} public interface AA : A {}  // CS0061 // OK public interface B {} internal interface BB : B {} internal interface C {} internal interface CC : C {}  
```