---
title: "Boxing (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# Boxing (C++/CX)
Beim *Boxing* wird eine Werttypvariable wie  [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) – oder ein grundlegender Skalartyp wie `int` – innerhalb einer Verweisklasse umgebrochen, wenn die Variable an eine Methode übergeben wird, die [Platform::Object^](../cppcx/platform-object-class.md) als Eingabetyp akzeptiert.  
  
## Übergeben eines Werttyps an einen Object^\-Parameter  
 Obwohl Sie für eine Variable nicht explizit Boxing anwenden müssen, um sie an einen Methodenparameter des Typs [Platform::Object^](../cppcx/platform-object-class.md) zu übergeben, müssen Sie eine Umwandlung zum ursprünglichen Typ explizit vornehmen, wenn Sie Werte abrufen, die zuvor geschachtelt wurden.  
  
 [!code-cpp[cx_boxing#01](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.cpp#01)]  
  
### Verwenden von Platform::IBox\<T\> zur Unterstützung von auf NULL festlegbare Werttypen  
 C\# und Visual Basic unterstützen das Konzept von Typen, die NULL\-Werte zulassen. In [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] können Sie den `Platform::IBox<T>`\-Typ verwenden, um öffentliche Methoden verfügbar zu machen, die Werttypparameter unterstützen, welche NULL\-Werte zulassen. Im folgenden Beispiel wird eine öffentliche [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Methode veranschaulicht, die NULL zurückgibt, wenn ein C\#\-Aufrufer für eines der Argumente NULL übergibt.  
  
 [!code-cpp[cx_boxing#02](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.h#02)]  
  
 In einem C\#\-XAML\-Client können Sie diese Methode wie folgt verwenden:  
  
```  
  
// C# client code BoxingDemo.Class1 obj = new BoxingDemo.Class1(); int? a = null; int? b = 5; var result = obj.Multiply(a,b); //result = null  
  
```  
  
## Siehe auch  
 [Typsystem \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Umwandlung von Typen \(C\+\+\/CX\)](../cppcx/casting-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)