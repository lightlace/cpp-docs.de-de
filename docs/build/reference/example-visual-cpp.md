---
title: '&lt;Beispiel > (C++ Dokumentations Kommentare)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 384e9b9808a49770887eeda69b1d24fdd3f06027
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988314"
---
# <a name="ltexamplegt"></a>&lt;example&gt;

Mit dem \<example>-Tag kann ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliothekmembers angegeben werden. In der Regel wird auch hier das Tag [\<code>](code-visual-cpp.md) verwendet.

## <a name="syntax"></a>Syntax

```
<example>description</example>
```

#### <a name="parameters"></a>Parameters

*Beschreibung*<br/>
Eine Beschreibung des Codebeispiels.

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```cpp
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

[XML-Dokumentation](xml-documentation-visual-cpp.md)
