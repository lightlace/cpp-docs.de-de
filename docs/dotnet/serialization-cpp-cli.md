---
title: Serialisierung (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: 794a71ae9a146b691ba6a4377a7fdf2c3ddd3501
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741388"
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
