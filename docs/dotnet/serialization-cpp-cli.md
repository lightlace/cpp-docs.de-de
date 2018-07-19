---
title: Serialisierung (C + c++ / CLI) | Microsoft Docs
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
ms.openlocfilehash: f4a410da74c37ee722c04f21e2cde906b9d061d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164561"
---
# <a name="serialization-ccli"></a>Serialisierung (C++/CLI)
Serialisierung (der Prozess des Speicherns des Status eines Objekts oder Mitglied auf einem permanenten Speichermedium) von verwalteten Klassen (einschließlich der einzelnen Felder oder Eigenschaften) wird unterstützt durch die <xref:System.SerializableAttribute> und <xref:System.NonSerializedAttribute> Klassen.  
  
## <a name="remarks"></a>Hinweise  
 Anwenden der **SerializableAttribute** benutzerdefinierten Attributs zur Verwendung einer verwalteten Klasse serialisiert die gesamte Klasse oder gelten nur für spezielle Felder oder Eigenschaften, die Teile der verwalteten Klasse serialisiert. Verwenden der **NonSerializedAttribute** benutzerdefinierten Attributs zur Felder und Eigenschaften einer verwalteten Klasse aus, das serialisiert wird.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel die Klasse `MyClass` (und die Eigenschaft `m_nCount`) ist als serialisierbar markiert. Allerdings die `m_nData` Eigenschaft wird nicht serialisiert, wie die **NonSerialized** benutzerdefiniertes Attribut:  
  
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
 Beachten Sie, dass beide Attribute unter Verwendung des Namens"short" verwiesen werden können (**Serializable** und **NonSerialized**). Dies wird ausführlich erläutert [Anwenden von Attributen](/dotnet/standard/attributes/applying-attributes).  
  
## <a name="see-also"></a>Siehe auch  
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)