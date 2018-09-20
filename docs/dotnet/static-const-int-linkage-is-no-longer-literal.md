---
title: Bindung von static Const Int Membern ist nicht mehr Literal | Microsoft-Dokumentation
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
ms.openlocfilehash: c51853274b061ba290ff90993f45ccdf3375349b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431293"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Die Bindung von static const int-Membern ist nicht mehr literal

Deklaration einer Konstante Member einer Klasse wurde von Managed Extensions für C++ in Visual C++ geändert.

Obwohl `static const` ganzzahligen Elemente werden weiterhin unterstützt, deren Verknüpfung-Attribut hat sich geändert. Ihre erste Bindungsattribut wird jetzt in einem Zeichenfolgenliteral ganzzahligen Member übertragen. Betrachten Sie beispielsweise die folgende Managed Extensions-Klasse:

```
public __gc class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

Die folgenden zugrunde liegenden CIL-Attribute für das Feld "" (Beachten Sie das literale Attribut) generiert:

```
.field public static literal int32
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

Obwohl dies in der neuen Syntax wird immer noch kompiliert:

```
public ref class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

Es gibt nicht mehr das literale Attribut aus, und daher nicht angezeigt wird als Konstante durch die CLR-Laufzeit:

```
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

Um das gleiche sprachübergreifenden-literal-Attribut ist, sollte die Deklaration geändert werden, die neu unterstützten `literal` Datenmember, wie folgt

```
public ref class Constants {
public:
   literal int LOG_DEBUG = 4;
};
```

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[Zeichenfolgenliteral](../windows/literal-cpp-component-extensions.md)