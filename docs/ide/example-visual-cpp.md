---
title: '&lt;example&gt; (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <example>
- example
dev_langs:
- C++
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e596d38b52e36c20c28eaab66e24805696865b17
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421660"
---
# <a name="ltexamplegt-visual-c"></a>&lt;example&gt; (Visual C++)

Mit dem \<example>-Tag kann ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliothekmembers angegeben werden. In der Regel wird auch hier das Tag [\<code>](../ide/code-visual-cpp.md) verwendet.

## <a name="syntax"></a>Syntax

```
<example>description</example>
```

#### <a name="parameters"></a>Parameter

*Beschreibung*<br/>
Eine Beschreibung des Codebeispiels.

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```
// xml_example_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_example_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>
   /// GetZero method
   /// </summary>
   /// <example> This sample shows how to call the GetZero method.
   /// <code>
   /// int main()
   /// {
   ///    return GetZero();
   /// }
   /// </code>
   /// </example>
   static int GetZero() {
      return 0;
   }
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)