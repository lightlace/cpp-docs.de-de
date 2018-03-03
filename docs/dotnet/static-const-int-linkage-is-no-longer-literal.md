---
title: "Static Const Int-Verknüpfung ist nicht mehr Literal | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8f34682fa780ef430d27104d3df9658f9e32ad39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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