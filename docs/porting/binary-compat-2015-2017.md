---
title: C++binäre Kompatibilität zwischen Visual Studio 2015 und Visual Studio 2019
ms.date: 10/17/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 761f6187a8b30ecb4214821c7f91d1b26e9c647c
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627019"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++binäre Kompatibilität zwischen Visual Studio 2015 und Visual Studio 2019

In Visual Studio 2013 und früheren Versionen war die Binärdateienkompatibilität zwischen Objektdateien (OBJ-Dateien), statischen Bibliotheken (LIB-Dateien), dynamischen Bibliotheken (DLL-Dateien) und ausführbaren Dateien (EXE-Dateien), die unter Verwendung verschiedener Versionen des Compilertoolsets und der Runtimebibliotheken erstellt wurden, nicht gewährleistet. 

In Visual Studio 2015 und höheren Versionen ist die Hauptversion des C++-Toolsets 14 (v140 für Visual Studio 2015, v141 für Visual Studio 2017 und v142 für Visual Studio 2019). Dies spiegelt die Tatsache wider, dass sowohl die Laufzeitbibliotheken als auch die Anwendungen, die mit einer dieser Versionen des Compilers kompiliert wurden, binär kompatibel sind. Dies bedeutet, dass Sie eine mit Visual Studio 2015 erstellte Drittanbieterbibliothek nicht noch mal kompilieren müssen, um sie aus einer Anwendung zu nutzen, die mit Visual Studio 2017 oder Visual Studio 2019 erstellt wurde.

Die einzige Ausnahme dieser Regel sind mit dem `/GL`-Compilerschalter kompilierte statische Bibliotheken oder Objektdateien, die nicht binärkompatibel sind.

Wenn Sie Binärdateien kombinieren, die mit unterschiedlichen unterstützten Versionen des MSVC-Toolsets erstellt wurden, darf die Visual C++ Redistributable, auf der Ihre Anwendung ausgeführt wird, nicht älter sein als eine der toolsetversionen, die zum Erstellen Ihrer APP verwendet werden, oder die darin genutzten Bibliotheken.

## <a name="upgrade-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Upgrade von Microsoft C++ Visual Redistributable von Visual Studio 2015 oder 2017 auf Visual Studio 2019

Da wir die binäre Kompatibilität beibehalten und die Hauptversion (14) für die Visual C++ Redistributable für Visual Studio 2015, 2017 und 2019 beibehalten haben, kann jeweils nur eine Version der Visual C++ Redistributable installiert werden. Eine neuere Version überschreibt ein älteres, das installiert ist. Wenn Sie über die Visual C++ Redistributable-Komponente von Visual Studio 2015 oder 2017 verfügen und später 2019 installieren, überschreibt die Version 2019 eine ältere Version. Da wir sicherstellen, dass die neueste Version alle neuesten Features und Fehlerbehebungen enthält, einschließlich Sicherheitskorrekturen, wird empfohlen, ein Upgrade auf die neueste verfügbare Version durchzuführen.

Ebenso ist es nicht zulässig, eine ältere Version von Visual C++ Redistributable auf einem Computer zu installieren, auf dem bereits eine neuere Version vorhanden ist. Wenn Sie das C++ Visual Redistributable-Element von Visual Studio 2015 oder 2017 auf einem Computer installieren, auf dem bereits 2019 vorhanden ist, führt dies zu einem Installationsfehler. Der Fehler sieht in etwa wie folgt aus:

```
*0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.*.
```

Dieser Fehler ist Entwurfs bedingt. Es wird empfohlen, die neueste Installation beizubehalten.

## <a name="see-also"></a>Siehe auch

* [Änderungsverlauf von Visual C++](../porting/visual-cpp-change-history-2003-2015.md)
* [Die neuesten unterstützten C++ visuellen verteilbaren Downloads](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
