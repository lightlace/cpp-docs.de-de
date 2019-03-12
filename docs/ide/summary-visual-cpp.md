---
title: '&lt;summary&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 32d939dc51e3e476e503f96995355fc78fb21ed0
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744853"
---
# <a name="ltsummarygt-visual-c"></a>&lt;summary&gt; (Visual C++)

Das \<summary>-Tag sollte verwendet werden, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](../ide/remarks-visual-cpp.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.

## <a name="syntax"></a>Syntax

```
<summary>description</summary>
```

#### <a name="parameters"></a>Parameter

*Beschreibung*<br/>
Eine Übersicht des Objekts.

## <a name="remarks"></a>Anmerkungen

Der Text für das \<summary>-Tag ist die einzige Informationsquelle über den Typ in IntelliSense und wird auch im [Objektkatalog](/visualstudio/ide/viewing-the-structure-of-code) und im Webbericht über Codekommentare angezeigt.

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
