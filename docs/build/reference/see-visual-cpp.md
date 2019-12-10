---
title: '&lt;siehe > (C++ Dokumentations Kommentare)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: 8693646fa37648d1b20c791d99d159f2c81b8ec1
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988618"
---
# <a name="ltseegt"></a>&lt;see&gt;

Mit dem \<see>-Tag kann ein Link im Text angegeben werden. Verwenden Sie [\<seealso>](seealso-visual-cpp.md), um Text anzugeben, der im Abschnitt „Siehe auch“ angezeigt werden soll.

## <a name="syntax"></a>Syntax

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parameters

*member*<br/>
Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und löst `member` in den Elementnamen in der XML-Ausgabe auf.  Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](doc-process-documentation-comments-c-cpp.md) kompiliert werden.

Ein Beispiel für die Verwendung von \<see> finden Sie unter [\<summary>](summary-visual-cpp.md).

Der MSVC-Compiler versucht, die Anmerkungen zu dieser Version in einem Durchlauf durch die Dokumentations Kommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert. Weitere Informationen finden Sie unter [\<seealso>](seealso-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie einen cref-Verweis auf einen generischen Typ erstellen, sodass der Compiler den Verweis auflöst.

```cpp
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
