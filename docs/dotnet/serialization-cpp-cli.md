---
title: Serialisierung (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ae8fe34cbb1307fc0d8799b9a0cd662a1a1fdde7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387574"
---
# <a name="serialization-ccli"></a>Serialisierung (C++/CLI)

Serialisierung (der Prozess des Speicherns des Status eines Objekts oder der Member, die auf einem permanenten Medium) von verwalteten Klassen (einschließlich der einzelnen Felder oder Eigenschaften) wird von unterstützt die <xref:System.SerializableAttribute> und <xref:System.NonSerializedAttribute> Klassen.

## <a name="remarks"></a>Hinweise

Anwenden der **SerializableAttribute** benutzerdefiniertes Attribut auf eine verwaltete Klasse an die gesamte Klasse zu serialisieren, oder wenden Sie nur auf bestimmte Felder oder Eigenschaften, die Teile der verwalteten Klasse serialisiert. Verwenden der **NonSerializedAttribute** benutzerdefiniertes Attribut auf Felder und Eigenschaften einer verwalteten Klasse von der Serialisierung.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden Beispiel die Klasse `MyClass` (und die Eigenschaft `m_nCount`) als serialisierbar markiert ist. Allerdings die `m_nData` Eigenschaft wird nicht serialisiert werden, wie durch die **NonSerialized** benutzerdefiniertes Attribut:

### <a name="code"></a>Code

```
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>Kommentare

Beachten Sie, dass beide Attribute mit ihren "short Name" verwiesen werden können (**Serializable** und **NonSerialized**). Dies wird weiter erläutert [Anwenden von Attributen](/dotnet/standard/attributes/applying-attributes).

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)