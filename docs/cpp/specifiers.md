---
title: Spezifizierer
ms.date: 11/04/2016
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
ms.openlocfilehash: aef967b26321f289cb8c7bd0402d7fe8f12b77b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330972"
---
# <a name="specifiers"></a>Spezifizierer

In diesem Thema wird beschrieben, die *Decl-Specifiers* -Komponente (deklarationsspezifizierer) einer [Deklaration](declarations-and-definitions-cpp.md).

Die folgenden Platzhalter und Sprachschlüsselwörter sind Deklarationsbezeichner:

*storage-class-specifier*

*type-specifier*

*function-specifier*

[friend](friend-cpp.md)

[typedef](aliases-and-typedefs-cpp.md) `(` *extended-decl-modifier-seq* `)`

[__declspec](declspec.md) `(` *extended-decl-modifier-seq* `)`

## <a name="remarks"></a>Hinweise

Die *Decl-Specifiers* Teil einer Deklaration ist die längste Sequenz von *Decl-Specifiers* , der als Typname, einschließlich der nicht den Zeiger oder verweismodifizierer erstellt werden können. Der Rest der Deklaration ist die *Deklarator*, der den eingeführten Namen enthält.

Die folgende Tabelle enthält vier Deklarationen und zeigt dann jede Deklaration des *Decl-Specifers* und *Deklarator* Komponente getrennt.

|Deklaration|*decl-specifiers*|`declarator`|
|-----------------|------------------------|------------------|
|`char *lpszAppName;`|**char**|`*lpszAppName`|
|`typedef char * LPSTR;`|**char**|`*LPSTR`|
|`const int func1();`|**const int**|`func1`|
|`volatile void *pvvObj;`|**flüchtige "void"**|`*pvvObj`|

Da **signiert**, **ohne Vorzeichen**, **lange**, und **kurze** impliziert alle **Int**,  **TypeDef** name eines dieser Schlüsselwörter folgt, werden Sie Mitglied der *Declarator-List* nicht *Decl-Specifiers*.

> [!NOTE]
>  Da ein Name neu deklariert werden kann, unterliegt seine Interpretation der letzten Deklaration im aktuellen Gültigkeitsbereich. Eine Neudeklaration kann beeinflussen, wie Namen insbesondere vom Compiler interpretiert werden **Typedef** Namen.

## <a name="see-also"></a>Siehe auch

[Deklarationen und Definitionen](declarations-and-definitions-cpp.md)
