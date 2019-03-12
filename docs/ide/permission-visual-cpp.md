---
title: '&lt;permission&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: ecf027600b23a640d1dc0cd68b75ffa5eb1b3659
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744613"
---
# <a name="ltpermissiongt-visual-c"></a>&lt;permission&gt; (Visual C++)

Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren. Mit der Klasse <xref:System.Security.PermissionSet> können Sie den Zugriff auf einen Member angeben.

## <a name="syntax"></a>Syntax

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>Parameter

*member*<br/>
Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.

Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.

Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../ide/see-visual-cpp.md).

*Beschreibung*<br/>
Eine Beschreibung des Zugriffs auf den Member

## <a name="remarks"></a>Anmerkungen

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

Der Visual C++-Compiler versucht, cref-Verweise in einem einzigen Durchlauf durch die Dokumentationskommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert. Weitere Informationen finden Sie unter [\<seealso>](../ide/seealso-visual-cpp.md).

## <a name="example"></a>Beispiel

```
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
