---
title: "Operator Windows::UI::Xaml::Interop::TypeName | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Operator Windows::UI::Xaml::Interop::TypeName
Ermöglicht die Konvertierung von `Platform::Type` in [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
## Syntax  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
## Rückgabewert  
 Gibt ein [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) zurück, wenn ein `Platform::Type^` angegeben wurde.  
  
## Hinweise  
 `TypeName` ist die sprachenneutrale Windows Runtime\-Struktur für die Darstellung von Typinformationen.[Platform::Type](../cppcx/platform-type-class.md) ist C\+\+\-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle \(ABI\) übergeben werden. Hier eine Verwendung von `TypeName` in der [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx)\-Funktion:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt die Umwandlung zwischen `TypeName` und `Type`.  
  
```  
  
// Convert from Type to TypeName Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## .NET Framework-Entsprechung  
 `TypeName` eines .NET Framework\-Programm\-Projekts als [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True).  
  
## Anforderungen  
  
## Siehe auch  
 [operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type\-Klasse](../cppcx/platform-type-class.md)