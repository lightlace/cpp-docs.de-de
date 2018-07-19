---
title: Static Const Int-Verknüpfung ist nicht mehr Literal | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cc3f72080c08807026c6458979ac0ba561e298df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164995"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Die Bindung von static const int-Membern ist nicht mehr literal
Die Deklaration eines Konstanten Members einer Klasse wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 Obwohl `static const` ganzzahligen Elemente werden weiterhin unterstützt, deren Verknüpfung-Attribut hat sich geändert. Die vorherige Verknüpfung-Attribut wird jetzt in einem Zeichenfolgenliteral ganzzahligen Member übertragen. Betrachten Sie beispielsweise die folgende Klasse von Managed Extensions:  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Die folgenden zugrunde liegenden CIL-Attribute für das Feld (Beachten Sie das literale Attribut) generiert:  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Während dies immer noch in der neuen Syntax kompiliert:  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Es gibt nicht mehr das literale Attribut, und daher nicht angezeigt wird als Konstante durch die CLR-Laufzeit:  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Um das gleiche literal zwischen Language-Attribut verfügen, sollte die Deklaration geändert werden, die neu unterstützten `literal` Datenmember wie folgt,  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + c++ / CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Zeichenfolgenliterale](../windows/literal-cpp-component-extensions.md)