---
title: "Compilerwarnung (Stufe 1) CS3001"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS3001"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3001"
ms.assetid: c4f3e247-5e47-4182-b415-c573fb1a152f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 1) CS3001
Der Argumenttyp "Typ" ist nicht CLS\-kompatibel  
  
 [Öffentliche](../Topic/public%20\(C%23%20Reference\).md), [geschützte](../Topic/protected%20\(C%23%20Reference\).md) oder `protected` `internal`\-Methoden müssen einen Parameter akzeptieren, dessen Typ mit der Common Language Specification \(CLS\) kompatibel ist. Weitere Informationen zur CLS\-Kompatibilität finden Sie unter [Schreiben von CLS\-kompatiblem Code](assetId:///4c705105-69a2-4e5e-b24e-0633bc32c7f3) und [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS3001 generiert:  
  
```  
// CS3001.cs [assembly:System.CLSCompliant(true)] public class a { public void bad(ushort i)   // CS3001 { } private void OK(ushort i)   // OK, private method { } public static void Main() { } }  
```