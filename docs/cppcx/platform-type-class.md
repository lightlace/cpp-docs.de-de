---
title: "Platform::Type-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Type-Klasse"
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Type-Klasse
Enthält Laufzeitinformationen über einen Typ, insbesondere einen Zeichenfolgennamen und einen Typecode. Wird durch Aufrufen einer [Object::GetType\-Methode](../cppcx/object-gettype-method.md) für ein Objekt oder durch Anwendung des Operators [typeid](~/windows/typeid-cpp-component-extensions.md) auf einen Klassen\- oder Strukturnamen abgerufen.  
  
## Syntax  
  
```cpp  
public ref class Platform::Type :      Platform::Object,      Platform::Details::IEquatable,      Platform::Details::IPrintable  
```  
  
## Hinweise  
 Die `Type`\-Klasse ist in Anwendungen nützlich, in denen die Verarbeitung über eine `if`\- oder `switch`\-Anweisung erfolgt, die sich je nach Laufzeittyp eines Objekts verzweigt. Der Typecode, der die Kategorie eines Typs beschreibt, wird über die Memberfunktion [Type::GetTypeCode\-Methode](../cppcx/type-gettypecode-method.md) abgerufen.  
  
## Öffentliche Methoden  
  
|||  
|-|-|  
|[Type::GetTypeCode\-Methode](../cppcx/type-gettypecode-method.md)|Gibt einen [Platform::TypeCode\-Enumeration](../cppcx/platform-typecode-enumeration.md)\-Wert für das Objekt zurück.|  
  
## Öffentliche Eigenschaften  
  
|||  
|-|-|  
|[Type::FullName\-Eigenschaft](../cppcx/type-fullname-property.md)|Gibt eine [Platform::String\-Klasse](../cppcx/platform-string-class.md)^ zurück, die den vollqualifizierten Namen des Typs darstellt, und verwendet . \(Punkt\) als Trennzeichen, nicht :: \(Doppelpunkte\) – z. B. "MyNamespace.MyClass".|  
  
## Konvertierungsoperatoren  
  
|||  
|-|-|  
|[Operator Type^](../cppcx/operator-subtracttype-hat.md)|Ermöglicht die Konvertierung von `Windows::UI::Xaml::Interop::TypeName` in `Platform::Type`.|  
|[Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|Ermöglicht die Konvertierung von `Platform::Type` in `Windows::UI::Xaml::Interop::TypeName`.|  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)