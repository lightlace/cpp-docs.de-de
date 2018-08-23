---
title: 'Platform:: Type Class | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
dev_langs:
- C++
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4d2931df50c6bfac126bc8e8ab1c70d61bdfe39
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596700"
---
# <a name="platformtype-class"></a>Platform::Type-Klasse
Enthält Laufzeitinformationen über einen Typ, insbesondere einen Zeichenfolgennamen und einen Typecode. Durch den Aufruf [Object:: GetType](../cppcx/platform-object-class.md#gettype) auf ein beliebiges Objekt oder die [Typeid](../windows/typeid-cpp-component-extensions.md) Operator auf eine Klasse oder Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class Platform::Type :      
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `Type` -Klasse ist in Anwendungen nützlich, in denen die Verarbeitung über eine `if` - oder `switch` -Anweisung erfolgt, die sich je nach Laufzeittyp eines Objekts verzweigt. Der Typcode, der die Kategorie eines Typs beschreibt wird abgerufen, mit der [Type:: GetTypeCode](#gettypecode) Member-Funktion.  
  
## <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|[Type::GetTypeCode-Methode](#gettypecode)|Gibt einen [Platform::TypeCode-Enumeration](../cppcx/platform-typecode-enumeration.md) -Wert für das Objekt zurück.| 
|[Type::ToString-Methode](#tostring)|Gibt den Namen des Typs in den Metadaten angegeben.| 

 
## <a name="public-properties"></a>Öffentliche Eigenschaften  
  
|||  
|-|-|  
|[Type:: FullName](#fullname)|Gibt eine [Platform::String-Klasse](../cppcx/platform-string-class.md)^ zurück, die den vollqualifizierten Namen des Typs darstellt, und verwendet . (Punkt) als Trennzeichen, nicht:: (Doppelpunkte) – z. B. `MyNamespace.MyClass`.|  
  
## <a name="conversion-operators"></a>Konvertierungsoperatoren  
  
|||  
|-|-|  
|[Operator Type^](../cppcx/operator-type-hat.md)|Ermöglicht die Konvertierung von `Windows::UI::Xaml::Interop::TypeName` in `Platform::Type`.|  
|[Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)|Ermöglicht die Konvertierung von `Platform::Type` in `Windows::UI::Xaml::Interop::TypeName`.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client (Min.):** Windows 8  
  
 **Unterstützter Server (Min.):** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

 
## <a name="fullname"></a> Type::FullName-Eigenschaft
Ruft ab, der den vollqualifizierten Namen des aktuellen Typs im Formular `Namespace.Type`.  
  
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

## <a name="tostring"></a> Type::ToString-Methode
Ruft ein den Namen des Typs.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::String^ ToString();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Name des Typs in den Metadaten angegeben.    
  
## <a name="see-also"></a>Siehe auch  
 [Platform-namespace](../cppcx/platform-namespace-c-cx.md)