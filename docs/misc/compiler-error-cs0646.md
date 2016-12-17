---
title: "Compilerfehler CS0646"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0646"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0646"
ms.assetid: 48ea306f-b4a0-4988-8d2b-ca9d38e9bdad
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0646
Das DefaultMember\-Attribut kann nicht für einen Typ angegeben werden, der einen Indexer enthält.  
  
 Wenn eine Klasse oder ein anderer Typ **System.Reflection.DefaultMemberAttribute** angibt, darf er keinen Indexer enthalten. Weitere Informationen finden Sie unter [Eigenschaften](../Topic/Properties%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0646 generiert:  
  
```  
// CS0646.cs // compile with: /target:library [System.Reflection.DefaultMemberAttribute("x")]   // CS0646 class MyClass { public int this[int index]   // an indexer { get { return 0; } } public int x = 0; } // OK [System.Reflection.DefaultMemberAttribute("x")] class MyClass2 { public int prop { get { return 0; } } public int x = 0; } class MyClass3 { public int this[int index]   // an indexer { get { return 0; } } public int x = 0; }  
```