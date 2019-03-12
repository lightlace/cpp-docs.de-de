---
title: '&lt;list&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C++ XML tag
- <list> C++ XML tag
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
ms.openlocfilehash: 015647cd381ba4dc0c099b322e3c5870246c9fc2
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751332"
---
# <a name="ltlistgt-visual-c"></a>&lt;list&gt; (Visual C++)

Der \<listheader>-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren. Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.

## <a name="syntax"></a>Syntax

```
<list type="bullet" | "number" | "table">
   <listheader>
      <term>term</term>
      <description>description</description>
   </listheader>
   <item>
      <term>term</term>
      <description>description</description>
   </item>
</list>
```

#### <a name="parameters"></a>Parameter

*term*<br/>
Ein zu definierender Begriff, der in `description` definiert wird.

*Beschreibung*<br/>
Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.

## <a name="remarks"></a>Anmerkungen

Jedes Element der Liste wird mit einem \<item>-Block angegeben. Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben. Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.

Eine Liste oder Tabelle kann so viele \<item>-Blöcke besitzen wie nötig.

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

```cpp
// xml_list_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_list_tag.dll
/// <remarks>Here is an example of a bulleted list:
/// <list type="bullet">
/// <item>
/// <description>Item 1.</description>
/// </item>
/// <item>
/// <description>Item 2.</description>
/// </item>
/// </list>
/// </remarks>
class MyClass {};
```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
