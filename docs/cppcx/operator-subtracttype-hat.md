---
title: Operator Type ^ | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8d51699d56f1868d5840665017feba2dec50766
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="operator-type"></a>Operator Type^
Ermöglicht die Konvertierung von [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) in `Platform::Type`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen `Platform::Type` zurück, wenn ein [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)angegeben wurde.  
  
### <a name="remarks"></a>Hinweise  
 `TypeName` ist die sprachenneutrale Windows Runtime-Struktur für die Darstellung von Typinformationen. [Platform::Type](../cppcx/platform-type-class.md) ist C++-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden. Hier eine Verwendung von `TypeName`in der [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) -Funktion:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Umwandlung zwischen `TypeName` und `Type`.  
  
```  
  
// Convert from Type to TypeName  
TypeName tn = TypeName(MainPage::typeid);  
  
// Convert back from TypeName to Type  
Type^ tx2 = (Type^)(tn);  
  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 .NET Framework-Programm-Projekts `TypeName` als [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).  
  
### <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch  
 [Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type-Klasse](../cppcx/platform-type-class.md)