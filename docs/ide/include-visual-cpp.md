---
title: '&lt;include&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- include
- <include>
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
ms.openlocfilehash: f0484d4158cf222ba4aae2aadf5e5352c8fc794f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740808"
---
# <a name="ltincludegt-visual-c"></a>&lt;include&gt; (Visual C++)

Mit dem \<include>-Tag können Sie auf Kommentare in einer anderen Datei verweisen, die die Typen und Member in Ihrem Quellcode beschreiben. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.  Sie können \<include> beispielsweise verwenden, um Standardkommentare einzufügen, die von Ihrem Team bzw. Unternehmen verwendet werden.

## <a name="syntax"></a>Syntax

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad qualifiziert werden.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  Der Compiler gibt eine Warnung aus, wenn er `filename` nicht findet.

*tagpath*<br/>
Ein gültiger XPath-Ausdruck, mit dem der gewünschte in der Datei enthaltene Knotensatz ausgewählt wird.

*name*<br/>
Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` besitzt eine `id`.

*ID*<br/>
Die ID für das Tag, das sich vor den Kommentaren befindet.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

## <a name="remarks"></a>Anmerkungen

Das \<include>-Tag verwendet die XPath-Syntax von XML. Weitere Anpassungsmöglichkeiten mithilfe von \<include> finden Sie in der XPath-Dokumentation.

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

Dies ist ein Beispiel einer Mehrfachdatei. Die erste Datei, die \<include> verwendet, enthält die folgenden Dokumentationskommentare:

```cpp
// xml_include_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_include_tag.dll

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />
public ref class Test {
   void TestMethod() {
   }
};

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />
public ref class Test2 {
   void Test() {
   }
};
```

Die zweite Datei, xml_include_tag.doc, enthält die folgenden Dokumentationskommentare:

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>Programmausgabe

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>t2</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
