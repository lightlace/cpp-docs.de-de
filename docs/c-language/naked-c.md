---
title: Naked (C)
ms.date: 11/04/2016
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
ms.openlocfilehash: 519d7bceb700e9862f0d0025b755cf28fb0fbc0c
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149777"
---
# <a name="naked-c"></a>Naked (C)

**Microsoft-spezifisch**

Das naked-Speicherklassenattribut ist eine Microsoft-spezifische Erweiterung der Programmiersprache C. Der Compiler generiert Code ohne Prolog- und Epilogcode für Funktionen, die mit dem naked-Speicherklassenattribut deklariert werden. Naked-Funktionen sind hilfreich, wenn Sie eigene Prolog-/Epilogcodesequenzen mithilfe des Inlineassemblercodes schreiben müssen. Naked-Funktionen sind für das Schreiben von virtuellen Gerätetreibern hilfreich.

Spezielle Informationen zur Verwendung des naked-Attributs finden Sie unter [Naked-Funktionen](../c-language/naked-functions.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)
