---
title: "Compilerwarnung (Stufe 1) CS1570"
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
  - "CS1570"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1570"
ms.assetid: a121d5c4-8b90-4cda-af5b-6ba8f23b2b1e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 1) CS1570
Der XML\-Kommentar für 'construct' enthält ungültigen XML\-Code — 'reason'  
  
 Bei Verwendung von [\/doc](../Topic/-doc%20\(C%23%20Compiler%20Options\).md) müssen alle Kommentare im Quellcode in XML sein. Fehler mit dem XML\-Markup generieren CS1570. Zum Beispiel:  
  
-   Wenn Sie eine Zeichenfolge an **cref** übergeben, etwa in einem [\<exception\>](../Topic/%3Cexception%3E%20\(C%23%20Programming%20Guide\).md)\-Tag, muss die Zeichenfolge in doppelte Anführungszeichen eingeschlossen werden.  
  
-   Wenn Sie ein Tag verwenden, das kein schließendes Tag aufweist, etwa [\<seealso\>](../Topic/%3Cseealso%3E%20\(C%23%20Programming%20Guide\).md), müssen Sie einen Schrägstrich vor der schließenden spitzen Klammer einfügen.  
  
-   Wenn Sie im Text der Beschreibung ein Größer\-als\- oder Kleiner\-als\-Zeichen verwenden möchten, müssen Sie dieses mit **&gt;** bzw. **&lt;** darstellen.  
  
-   Das Datei\- oder Pfadattribut für ein [\<include\>](../Topic/%3Cinclude%3E%20\(C%23%20Programming%20Guide\).md)\-Tag fehlte oder wurde falsch formatiert.  
  
 Im folgenden Beispiel wird CS1570 generiert:  
  
```  
// CS1570.cs // compile with: /W:1 namespace ns { // the following line generates CS1570 /// <summary> returns true if < 5 </summary> // try this instead // /// <summary> returns true if <5 </summary> public class MyClass { public static void Main () { } } }  
```