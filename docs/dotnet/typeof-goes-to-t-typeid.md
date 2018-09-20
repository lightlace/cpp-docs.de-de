---
title: 'Typeof wird zu t:: typeid | Microsoft-Dokumentation'
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
ms.openlocfilehash: 4433061fceef455685b6588c81c8c2e434253433
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374674"
---
# <a name="typeof-goes-to-ttypeid"></a>typeof wird zu T::typeid

Die `typeof` Operator verwendet in Managed Extensions für C++ durch ersetzen die `typeid` -Schlüsselwort in Visual C++.

In Managed Extensions die `__typeof()` Operator gibt das zugeordnete `Type*` Objekt, wenn der Name eines verwalteten Typs übergeben. Zum Beispiel:

```
// Creates and initializes a new Array instance.
Array* myIntArray =
   Array::CreateInstance( __typeof(Int32), 5 );
```

In der neuen Syntax `__typeof` wurde ersetzt durch eine weitere Form der `typeid` zurückgibt, die eine `Type^` Wenn ein verwalteter Typ angegeben wird.

```
// Creates and initializes a new Array instance.
Array^ myIntArray =
   Array::CreateInstance( Int32::typeid, 5 );
```

## <a name="see-also"></a>Siehe auch

[Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[typeid](../windows/typeid-cpp-component-extensions.md)