---
title: Operator TypeName | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50c7b6a8e62aa957c54f66ebaf87fcd86df458fb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199342"
---
# <a name="operator-windowsuixamlinteroptypename"></a>Operator Windows::UI::Xaml::Interop::TypeName
Ermöglicht die Konvertierung von `Platform::Type` zu [TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine [TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) bei einem `Platform::Type^`.  
  
### <a name="remarks"></a>Hinweise  
 `TypeName` ist die sprachenneutrale Windows Runtime-Struktur für die Darstellung von Typinformationen. [Platform::Type](../cppcx/platform-type-class.md) ist C++-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden. Hier ist eine Verwendung von `TypeName`in die [Navigate](https://msdn.microsoft.com/library/windows/apps/hh702394.aspx) Funktion:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Umwandlung zwischen `TypeName` und `Type`.  
  
```  
  
// Convert from Type to TypeName  
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);  
  
// Convert back from TypeName to Type  
Type^ tx2 = (Type^)(tn);  
  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 .NET Framework-Programm-Projekts `TypeName` als [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).  
  
### <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch  
 [TypeName-Operator](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type-Klasse](../cppcx/platform-type-class.md)