---
title: '&lt;seealso&gt; (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <seealso>
- seealso
dev_langs:
- C++
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69cbf45ee37ff10f5b367bc3915647815b2ccd09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376472"
---
# <a name="ltseealsogt-visual-c"></a>&lt;seealso&gt; (Visual C++)

Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen. Mit [\<see>](../ide/see-visual-cpp.md) kann ein Link im Text angegeben werden.

## <a name="syntax"></a>Syntax

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parameter

*member*<br/>
Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und löst `member` in den Elementnamen in der XML-Ausgabe auf.  Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.

Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../ide/see-visual-cpp.md).

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](../ide/summary-visual-cpp.md).

Der Visual C++-Compiler versucht, cref-Verweise in einem einzigen Durchlauf durch die Dokumentationskommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein nicht aufgelöstes Symbol in einem cref-Verweis referenziert. Der XML-Kommentar für den cref-Verweis auf B::Test ist `<seealso cref="!:B::Test" />`, der Verweis auf A::Test ein wohlgeformtes `<seealso cref="M:A.Test" />`.

```
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

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)