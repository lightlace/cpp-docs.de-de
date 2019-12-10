---
title: '&lt;Wert > (C++ Dokumentations Kommentare)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: de84d1faca59a6c8e4f82fba3605cbd54a05bd2e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988590"
---
# <a name="ltvaluegt"></a>&lt;Wert&gt;

Mit dem Tag \<value> können Sie Eigenschaften und Eigenschaftenaccessormethoden beschreiben. Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe eines Code-Assistenten in der Visual Studio-IDE der neuen Eigenschaft ein [\<summary>](summary-visual-cpp.md)-Tag hinzugefügt wird. Sie sollten dann manuell ein \<value>-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.

## <a name="syntax"></a>Syntax

```
<value>property-description</value>
```

#### <a name="parameters"></a>Parameters

*property-description*<br/>
Eine Beschreibung der Eigenschaft

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```cpp
// xml_value_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_value_tag.dll
using namespace System;
/// Text for class Employee.
public ref class Employee {
private:
   String ^ name;
   /// <value>Name accesses the value of the name data member</value>
public:
   property String ^ Name {
      String ^ get() {
         return name;
      }
      void set(String ^ i) {
         name = i;
      }
   }
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](xml-documentation-visual-cpp.md)
