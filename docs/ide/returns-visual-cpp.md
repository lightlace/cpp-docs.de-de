---
title: '&lt;returns&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: 7861d57d474db3c45b2c773a057a545c15602822
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740845"
---
# <a name="ltreturnsgt-visual-c"></a>&lt;returns&gt; (Visual C++)

Das \<returns>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um den Rückgabewert zu beschreiben.

## <a name="syntax"></a>Syntax

```
<returns>description</returns>
```

#### <a name="parameters"></a>Parameter

*Beschreibung*<br/>
Eine Beschreibung des Rückgabewerts.

## <a name="remarks"></a>Anmerkungen

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```
// xml_returns_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_returns_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <returns>Returns zero.</returns>
   int GetZero() { return 0; }
};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
