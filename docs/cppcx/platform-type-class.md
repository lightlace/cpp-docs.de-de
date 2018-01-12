---
title: 'Platform:: Type-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
dev_langs: C++
helpviewer_keywords: Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c292426b9d04fd5b3d9785224f9b2d48f129f0db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformtype-class"></a>Platform::Type-Klasse
Enthält Laufzeitinformationen über einen Typ, insbesondere einen Zeichenfolgennamen und einen Typecode. Durch den Aufruf von [GetType](../cppcx/platform-object-class.md#gettype) für ein Objekt oder oder über die [Typeid](../windows/typeid-cpp-component-extensions.md) Operator auf eine Klassen- oder Strukturnamen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class Platform::Type :      
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `Type` -Klasse ist in Anwendungen nützlich, in denen die Verarbeitung über eine `if` - oder `switch` -Anweisung erfolgt, die sich je nach Laufzeittyp eines Objekts verzweigt. Der Code, der die Kategorie eines Typs beschreibt wird abgerufen, wobei die [Type:: GetTypeCode](#gettypecode) Memberfunktion.  
  
## <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|[Type::GetTypeCode-Methode](#gettypecode)|Gibt einen [Platform::TypeCode-Enumeration](../cppcx/platform-typecode-enumeration.md) -Wert für das Objekt zurück.| 
|[Type::ToString-Methode](#tostring)|Gibt den Namen des Typs entsprechend den Angaben in seinen Metadaten zurück.| 

 
## <a name="public-properties"></a>Öffentliche Eigenschaften  
  
|||  
|-|-|  
|[Type:: FullName](#fullname)|Gibt eine [Platform::String-Klasse](../cppcx/platform-string-class.md)^ zurück, die den vollqualifizierten Namen des Typs darstellt, und verwendet . (Punkt) als Trennzeichen, nicht:: (Doppelpunkte) – z. B. `MyNamespace.MyClass`.|  
  
## <a name="conversion-operators"></a>Konvertierungsoperatoren  
  
|||  
|-|-|  
|[Operator Type^](../cppcx/operator-subtracttype-hat.md)|Ermöglicht die Konvertierung von `Windows::UI::Xaml::Interop::TypeName` in `Platform::Type`.|  
|[Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|Ermöglicht die Konvertierung von `Platform::Type` in `Windows::UI::Xaml::Interop::TypeName`.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

 
## <a name="fullname"></a> Type::FullName-Eigenschaft
Ruft den vollqualifizierten Namen des aktuellen Typs im Formular `Namespace.Type`.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
String^ FullName();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des Typs.  
### <a name="example"></a>Beispiel  
  
```  
  
//  namespace is TestApp  
MainPage::MainPage()  
{  
    InitializeComponent();  
    Type^ t = this->GetType();  
    auto s = t->FullName; // returns "TestApp.MainPage"  
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"  
}  
```  
  


## <a name="gettypecode"></a> Type::GetTypeCode-Methode
Ruft einen der eingebauten Typen aus der Kategorie der numerischen Typen ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der Platform::TypeCode-Enumierationswerte.  
  
### <a name="remarks"></a>Hinweise  
 Das Äquivalent der GetTypeCode()-Membermethode ist die `typeid` Eigenschaft.

## <a name="tostring"></a>Type::ToString-Methode
Ruft ein den Namen des Typs.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::String^ ToString();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Name des Typs entsprechend den Angaben in seinen Metadaten.    
  
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)