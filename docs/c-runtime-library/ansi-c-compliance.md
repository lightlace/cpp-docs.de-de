---
title: ANSI C-Kompatibilität
ms.date: 11/04/2016
f1_keywords:
- Ansi
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
ms.openlocfilehash: 7a4462e84ec01bd236849c6aed024b636b315243
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742827"
---
# <a name="ansi-c-compliance"></a>ANSI C-Kompatibilität

Die Namenskonvention für alle Microsoft-spezifischen Bezeichner im Laufzeitsystem (z.B. Funktionen, Makros, Konstanten, Variablen und Typdefinitionen) ist ANSI-kompatibel. In dieser Dokumentation wird jede Laufzeitfunktion, die den Standards ANSI/ISO C entspricht, als ANSI-kompatibel aufgeführt. ANSI-kompatible Anwendungen sollten nur diese ANSI-kompatiblen Funktionen verwenden.

Die Namen der Microsoft-spezifischen Funktionen und globalen Variablen beginnen mit einem einzelnen Unterstrich. Diese Namen können nur lokal innerhalb des Bereichs Ihres Codes überschrieben werden. Wenn Sie z.B. die Microsoft-Laufzeitheaderdateien einbeziehen, können Sie weiterhin die Microsoft-spezifische Funktion `_open` lokal überschreiben, indem Sie eine lokale Variable mit demselben Namen deklarieren. Allerdings können Sie diesen Namen nicht für Ihre eigene globale Funktion oder globale Variable verwenden.

Die Namen von Microsoft-spezifischen Makros und Manifestkonstanten beginnen mit zwei Unterstrichen oder einem einzelnen vorangestellten Unterstrich, direkt gefolgt von einem Großbuchstaben. Der Bereich dieser Bezeichner ist absolut. Sie können aus diesem Grund beispielsweise nicht den Microsoft-spezifischen Bezeichner **_UPPER** verwenden.

## <a name="see-also"></a>Siehe auch

[Kompatibilität](../c-runtime-library/compatibility.md)
