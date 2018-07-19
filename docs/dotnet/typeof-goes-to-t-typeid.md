---
title: 'Typeof wird zu t:: typeid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ae9f772a68735555748e6edbeb6196f1a73d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164517"
---
# <a name="typeof-goes-to-ttypeid"></a>typeof wird zu T::typeid
Die `typeof` Operator wird in Managed Extensions für C++ durch Ersetzen der `typeid` -Schlüsselwort in Visual C++.  
  
 In Managed Extensions die `__typeof()` Operator gibt das zugeordnete `Type*` Objekt, wenn der Name eines verwalteten Typs übergeben. Zum Beispiel:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 In der neuen Syntax `__typeof` wurde ersetzt durch eine weitere Form der `typeid` zurückgegeben, die eine `Type^` Wenn ein verwalteter Typ angegeben wird.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Sprachänderungen (C + c++ / CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)