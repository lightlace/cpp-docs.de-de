---
title: Vorlagenverweisklassen (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: 3e9c233b5227b4ad86eb632db740001bc2a3a8bd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740853"
---
# <a name="template-ref-classes-ccx"></a>Vorlagenverweisklassen (C++/CX)

C++-Vorlagen werden nicht in Metadaten veröffentlicht und können daher in Ihrem Programm keine öffentliche oder geschützte Barrierefreiheit haben. Sie können C++-Standardvorlagen selbstverständlich intern im Programm verwenden. Außerdem können Sie eine private Verweisklasse als Vorlage definieren und eine explizit spezialisierte Vorlagenverweisklasse als privaten Member in einer öffentlichen Verweisklasse deklarieren.

## <a name="authoring-ref-class-templates"></a>Erstellen von Verweisklassenvorlagen

Im folgenden Beispiel wird gezeigt, wie eine private Verweisklasse als Vorlage und wie eine C++-Standardvorlage deklariert wird und wie beide als Member in einer öffentlichen Verweisklasse deklariert werden. Beachten Sie, dass C++ die Standardvorlage durch einen Windows-Runtime-Typ, in diesem Fall Platform:: String ^, spezialisiert werden kann.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Siehe auch

[Typsystem (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++-/CX-Programmiersprachenreferenz](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Referenz zu Namespaces](../cppcx/namespaces-reference-c-cx.md)
