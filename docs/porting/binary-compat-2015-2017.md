---
title: C++binäre Kompatibilität zwischen Visual Studio 2015 und Visual Studio 2019
description: Beschreibt, wie die binäre Kompatibilität zwischen C++ kompilierten Dateien in Visual Studio 2015, 2017 und 2019 funktioniert. Ein Microsoft Visual C++ Redistributable Package funktioniert für alle drei Versionen.
ms.date: 11/07/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: e41c34abe25deefe100f525044faeac0b0c3054a
ms.sourcegitcommit: eb254b4462a58d219376ff501bf768bd1adc07ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2019
ms.locfileid: "73912883"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++binäre Kompatibilität zwischen Visual Studio 2015 und Visual Studio 2019

In Microsoft Visual Studio 2013 und früheren Versionen wird die binäre Kompatibilität zwischen Objektdateien (OBJS), statischen Bibliotheken (lib), Dynamic Link Libraries (DLLs) und ausführbaren Dateien (exe-Dateien), die mit verschiedenen Versionen des compilertoolsets erstellt wurden, nicht garantiert. und Laufzeitbibliotheken.

In Visual Studio 2015 und höheren Versionen ist die Hauptversion des C++-Toolsets 14 (v140 für Visual Studio 2015, v141 für Visual Studio 2017 und v142 für Visual Studio 2019). Diese Nummerierung spiegelt die Tatsache wider, dass sowohl die Laufzeitbibliotheken als auch die Anwendungen, die mit einer dieser Versionen des Compilers kompiliert wurden, binär kompatibel sind. Wenn Sie also über eine Bibliothek eines Drittanbieters verfügen, die mit Visual Studio 2015 erstellt wurde, müssen Sie Sie nicht erneut kompilieren, um Sie aus einer Anwendung zu nutzen, die mit Visual Studio 2017 oder Visual Studio 2019 erstellt wurde.

Die einzige Ausnahme von dieser Regel ist, dass statische Bibliotheken oder Objektdateien, die mit dem `/GL`-Compilerschalter kompiliert werden, *nicht* binär kompatibel sind.

Wenn Sie Binärdateien kombinieren, die mit unterschiedlichen unterstützten C++ Versionen des Microsoft-Toolsets (MSVC C++ ) erstellt wurden, kann das verteilbare verteilbare Paket, auf dem Ihre Anwendung ausgeführt wird, nicht älter sein als eine der toolsetversionen, die zum Erstellen Ihrer APP verwendet werden, oder alle verwendeten Bibliotheken.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Upgrade von Microsoft Visual C++ Redistributable von Visual Studio 2015 oder 2017 auf Visual Studio 2019

Da wir die binäre Kompatibilität beibehalten und die Hauptversion (14) in der Microsoft Visual C++ Redistributable für Visual Studio 2015, 2017 und 2019 beibehalten haben, kann jeweils nur eine Version der Visual C++ Redistributable installiert werden. Eine neuere Version überschreibt eine ältere Version, die bereits installiert ist. Wenn Sie über Visual Studio C++ 2015 oder 2017 Visual Redistributable verfügen und später Visual Studio 2019 installieren, überschreibt die Version 2019 die ältere Version. Da wir sicherstellen, dass die neueste Version über alle neuesten Features und Fehlerbehebungen verfügt (einschließlich Sicherheitskorrekturen), empfehlen wir immer, ein Upgrade auf die neueste verfügbare Version durchzuführen.

Auf ähnliche Weise können Sie auf einem Computer, auf dem bereits eine C++ neuere Version installiert ist, keine ältere Version von Visual Redistributable installieren. Wenn Sie das C++ Visual Redistributable-Element von Visual Studio 2015 oder 2017 auf einem Computer installieren, auf dem die Version 2019 bereits vorhanden ist, wird ein Installationsfehler ausgelöst. Der Fehler ähnelt dem folgenden:

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

Dieser Fehler ist Entwurfs bedingt. Es wird empfohlen, die neueste Version zu installieren.

## <a name="see-also"></a>Siehe auch

* [Änderungsverlauf von Visual C++](../porting/visual-cpp-change-history-2003-2015.md)
* [Die neuesten unterstützten C++ visuellen verteilbaren Downloads](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
