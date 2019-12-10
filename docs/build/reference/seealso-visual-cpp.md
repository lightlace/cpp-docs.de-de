---
title: '&lt;seeauch > (C++ Dokumentations Kommentare)'
ms.date: 11/04/2016
f1_keywords:
- <seealso>
- seealso
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
ms.openlocfilehash: 698db2df462f561acd897d0d0e56b3106a915466
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988607"
---
# <a name="ltseealsogt"></a>&lt;seealso&gt;

Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen. Mit [\<see>](see-visual-cpp.md) kann ein Link im Text angegeben werden.

## <a name="syntax"></a>Syntax

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parameters

*member*<br/>
Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und löst `member` in den Elementnamen in der XML-Ausgabe auf.  Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.

Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](see-visual-cpp.md).

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](doc-process-documentation-comments-c-cpp.md) kompiliert werden.

Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](summary-visual-cpp.md).

Der MSVC-Compiler versucht, die Anmerkungen zu dieser Version in einem Durchlauf durch die Dokumentations Kommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein nicht aufgelöstes Symbol in einem cref-Verweis referenziert. Der XML-Kommentar für den cref-Verweis auf B::Test ist `<seealso cref="!:B::Test" />`, der Verweis auf A::Test ein wohlgeformtes `<seealso cref="M:A.Test" />`.

```cpp
// xml_seealso_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_seealso_tag.dll

/// Text for class A.
public ref struct A {
   /// <summary><seealso cref="A::Test"/>
   /// <seealso cref="B::Test"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void Test() {}
};

/// Text for class B.
public ref struct B {
   void Test() {}
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](xml-documentation-visual-cpp.md)
