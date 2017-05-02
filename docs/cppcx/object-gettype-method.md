---
title: "Object::GetType-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetType"
ms.assetid: f633d71a-ff80-49f9-931d-189c00b1f6c5
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetType-Methode
Gibt ein [Platform::Type](../cppcx/platform-type-class.md)\-Objekt zurück, das den Laufzeittyp eines Objekts beschreibt.  
  
## Syntax  
  
```vb  
Object::GetType()  
```  
  
```csharp  
  
```  
  
## Eigenschaftswert\/Rückgabewert  
 Ein [Platform::Type](../cppcx/platform-type-class.md)\-Objekt, das den Laufzeittyp des Objekts beschreibt.  
  
## Hinweise  
 Die statische [Type::GetTypeCode\-Methode](../cppcx/type-gettypecode-method.md) kann verwendet werden, um einen [Platform::TypeCode\-Enumeration](../cppcx/platform-typecode-enumeration.md)\-Wert abzurufen, der den aktuellen Typ darstellt. Dies ist besonders für integrierte Typen hilfreich. Der Typencode für eine Verweisklasse außer [Platform::String](../cppcx/platform-string-class.md) ist Objekt \(1\).  
  
 Die [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)\-Klasse wird in den Windows\-APIs als sprachenunabhängige Methode für die Übergabe von Typinformationen zwischen Windows\-Komponenten und \-Apps verwendet. T [Platform::Type\-Klasse](../cppcx/platform-type-class.md) verfügt über Operatoren zum Konvertieren zwischen `Type` und `TypeName`.  
  
 Verwenden Sie den Operator [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md), um ein `Platform::Type`\-Objekt für einen Klassennamen zurückzugeben, zum Beispiel beim Navigieren zwischen XAML\-Seiten:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## Siehe auch  
 [Platform::Type\-Klasse](../cppcx/platform-type-class.md)   
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)   
 [Typsystem](../cppcx/type-system-c-cx.md)