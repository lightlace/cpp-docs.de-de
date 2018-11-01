---
title: Vorlagenverweisklassen (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: a128b9fcc7b37ad2cf7c7a17abb24c8074952501
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642208"
---
# <a name="template-ref-classes-ccx"></a>Vorlagenverweisklassen (C++/CX)

C++-Vorlagen werden nicht in Metadaten veröffentlicht und können daher in Ihrem Programm keine öffentliche oder geschützte Barrierefreiheit haben. Sie können C++-Standardvorlagen selbstverständlich intern im Programm verwenden. Außerdem können Sie eine private Verweisklasse als Vorlage definieren und eine explizit spezialisierte Vorlagenverweisklasse als privaten Member in einer öffentlichen Verweisklasse deklarieren.

## <a name="authoring-ref-class-templates"></a>Erstellen von Verweisklassenvorlagen

Im folgenden Beispiel wird gezeigt, wie eine private Verweisklasse als Vorlage und wie eine C++-Standardvorlage deklariert wird und wie beide als Member in einer öffentlichen Verweisklasse deklariert werden. Beachten Sie, dass die C++-Standardvorlage spezialisiert werden kann, von einem Windows-Runtime-Typ, in diesem Fall ein Platform:: String ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Siehe auch

[Typsystem (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)