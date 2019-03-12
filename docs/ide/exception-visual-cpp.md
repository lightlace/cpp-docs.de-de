---
title: '&lt;exception&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
ms.openlocfilehash: f30ae7e36c0540c98eecf2c9f73fbd23df230663
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748189"
---
# <a name="ltexceptiongt-visual-c"></a>&lt;exception&gt; (Visual C++)

Mit dem Tag \<exception> können Sie angeben, welche Ausnahmen ausgelöst werden können. Dieses Tag wird auf eine Methodendefinition angewendet.

## <a name="syntax"></a>Syntax

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>Parameter

*member*<br/>
Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist. Der Compiler prüft mithilfe von Regeln für die Namenssuche, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.  Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.

Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../ide/see-visual-cpp.md).

*Beschreibung*<br/>
Steht für eine Beschreibung.

## <a name="remarks"></a>Anmerkungen

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

Der Visual C++-Compiler versucht, cref-Verweise in einem einzigen Durchlauf durch die Dokumentationskommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert. Weitere Informationen finden Sie unter [\<seealso>](../ide/seealso-visual-cpp.md).

## <a name="example"></a>Beispiel

```
// xml_exception_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_exception_tag.dll
using namespace System;

/// Text for class EClass.
public ref class EClass : public Exception {
   // class definition ...
};

/// <exception cref="System.Exception">Thrown when... .</exception>
public ref class TestClass {
   void Test() {
      try {
      }
      catch(EClass^) {
      }
   }
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
