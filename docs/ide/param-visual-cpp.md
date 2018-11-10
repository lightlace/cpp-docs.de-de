---
title: '&lt;param&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: ec570a1c8b66e12474a2d960ed1b4f4b5e21b219
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651333"
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)

Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.

## <a name="syntax"></a>Syntax

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>Parameter

*name*<br/>
Der Name eines Methodenparameters.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  Der Compiler gibt eine Warnung aus, wenn er `name` nicht findet.

*Beschreibung*<br/>
Eine Beschreibung für den Parameter

## <a name="remarks"></a>Hinweise

Der Text für das \<param>-Tag wird in IntelliSense, dem [Objektkatalog](/visualstudio/ide/viewing-the-structure-of-code), und im Webbericht für Codekommentare angezeigt.

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```cpp
// xml_param_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_param_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <param name="Int1">Used to indicate status.</param>
   void MyMethod(int Int1) {
   }
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)