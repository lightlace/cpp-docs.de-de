---
title: '&lt;finden Sie unter > (C++-Dokumentationskommentare)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: be99d3ac156c587888a7c56997d82531cf86ccec
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825889"
---
# <a name="ltseegt"></a>&lt;see&gt;

Mit dem \<see>-Tag kann ein Link im Text angegeben werden. Verwenden Sie [\<seealso>](seealso-visual-cpp.md), um Text anzugeben, der im Abschnitt „Siehe auch“ angezeigt werden soll.

## <a name="syntax"></a>Syntax

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parameter

*member*<br/>
Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und löst `member` in den Elementnamen in der XML-Ausgabe auf.  Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](doc-process-documentation-comments-c-cpp.md) kompiliert werden.

Ein Beispiel für die Verwendung von \<see> finden Sie unter [\<summary>](summary-visual-cpp.md).

Der MSVC-Compiler versucht, Cref-Verweise in einem einzigen Durchlauf durch die Dokumentationskommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert. Weitere Informationen finden Sie unter [\<seealso>](seealso-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie einen cref-Verweis auf einen generischen Typ erstellen, sodass der Compiler den Verweis auflöst.

```
// xml_see_cref_example.cpp
// compile with: /LD /clr /doc
// the following cref shows how to specify the reference, such that,
// the compiler will resolve the reference
/// <see cref="C{T}">
/// </see>
ref class A {};

// the following cref shows another way to specify the reference,
// such that, the compiler will resolve the reference
/// <see cref="C < T >"/>

// the following cref shows how to hard-code the reference
/// <see cref="T:C`1">
/// </see>
ref class B {};

/// <see cref="A">
/// </see>
/// <typeparam name="T"></typeparam>
generic<class T>
ref class C {};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](xml-documentation-visual-cpp.md)
