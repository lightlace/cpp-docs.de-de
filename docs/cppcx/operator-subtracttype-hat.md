---
title: "Operator Type^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Operator Type^
Ermöglicht die Konvertierung von [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) in `Platform::Type`.  
  
## Syntax  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
## Rückgabewert  
 Gibt einen `Platform::Type` zurück, wenn ein [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) angegeben wurde.  
  
## Hinweise  
 `TypeName` ist die sprachenneutrale Windows Runtime\-Struktur für die Darstellung von Typinformationen.[Platform::Type](../cppcx/platform-type-class.md) ist C\+\+\-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle \(ABI\) übergeben werden. Hier eine Verwendung von `TypeName` in der [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx)\-Funktion:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt die Umwandlung zwischen `TypeName` und `Type`.  
  
```  
  
// Convert from Type to TypeName TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## .NET Framework-Entsprechung  
 `TypeName` eines .NET Framework\-Programm\-Projekts als [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True).  
  
## Anforderungen  
  
## Siehe auch  
 [Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type\-Klasse](../cppcx/platform-type-class.md)